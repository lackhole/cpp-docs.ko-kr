---
title: '방법: C + + Interop를 사용 하 여 콜백 및 대리자 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
ms.openlocfilehash: d3814ffbcd23168a9727b1b1d73e2c825639a9c5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739225"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>방법: C + + Interop를 사용 하 여 콜백 및 대리자 마샬링

이 항목에서는 마샬링하는 방법을 보여 줍니다 및 Visual c + +를 사용 하 여 관리 및 비관리 코드 간에 대리자 (콜백을 관리 되는 버전).

다음 코드 예제에서 사용 된 [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md) 구현 #pragma 지시문 관리는 관리 되지 않는 함수에서 동일한 파일에서 함수는 별도 파일에 정의할 수 있습니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 합니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 관리 되는 대리자를 트리거하는 관리 되지 않는 API를 구성 하는 방법에 설명 합니다. 관리 되는 대리자가 만들어진 interop 메서드 중 하나 및 <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, 대리자에 대 한 기본 진입점을 검색 하는 데 사용 됩니다. 그러면이 주소 지식이 없는 관리 되는 함수로 구현 되는 팩트를 사용 하 여 호출 하는 관리 되지 않는 함수에 전달 됩니다.

알 수 있습니다 하는 것이 가능 하지만 pin에 필요 하지 않은 사용 하 여 대리자 [pin_ptr (C + + CLI)](../windows/pin-ptr-cpp-cli.md) 재배치 하거나 가비지 수집기에 의해 삭제 하지 못하게 합니다. 중간 가비지 수집을 방지가 필요 하지만 고정 컬렉션을 방지 하지만 또한 재배치를 방지 하는 대로 필요한 것 보다 더 많은 보호를 제공 합니다.

대리자를 가비지 컬렉션에서 찾을 다시는 아무런 영향이 없습니다 해도 내부에 있는 관리 되는 콜백 따라서 <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> 대리자를 대리자의 재배치를 허용 하지만 삭제를 방지에 대 한 참조를 추가 하는 데 사용 됩니다. Pin_ptr 대신 GCHandle을 사용 하면 관리 되는 힙의 조각화 가능성이 줄어듭니다.

```
// MarshalDelegate1.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);

int TakesCallback(ANSWERCB fp, int n, int m) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n, m);
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   return n + m;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   GCHandle gch = GCHandle::Alloc(fp);
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

// force garbage collection cycle to prove
// that the delegate doesn't get disposed
   GC::Collect();

   int answer = TakesCallback(cb, 243, 257);

// release reference to delegate
   gch.Free();
}
```

## <a name="example"></a>예제

다음 예제는 이전 예제와 유사 하지만 경우 제공 된 함수 포인터를 저장 되어 관리 되지 않는 API에서 호출할 수 있습니다 언제 든 지는 임의의 기간 동안 가비지 수집 하지 않을 필요 합니다. 결과적으로, 다음 예제에서는의 전역 인스턴스 <xref:System.Runtime.InteropServices.GCHandle> 대리자 이동, 함수 범위의 독립적인 하지 못하도록 합니다. 첫 번째 예제에서 설명 했 듯이 pin_ptr를 사용 하 여 이러한 예제를 보려면 필요는 없지만 경우 작동 하지 않습니다, pin_ptr의 범위는 단일 함수로 제한 합니다.

```
// MarshalDelegate2.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);
static ANSWERCB cb;

int TakesCallback(ANSWERCB fp, int n, int m) {
   cb = fp;
   if (cb) {
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);
      return cb(n, m);
   }
   printf_s("[unmanaged] unregistering callback");
   return 0;
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;

   return n + m + x;
}

static GCHandle gch;

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);

   gch = GCHandle::Alloc(fp);

   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TakesCallback(cb, 243, 257);

   // possibly much later (in another function)...

   Console::WriteLine("[managed] releasing callback mechanisms...");
   TakesCallback(0, 243, 257);
   gch.Free();
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
