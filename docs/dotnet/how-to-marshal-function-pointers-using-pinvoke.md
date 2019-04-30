---
title: '방법: PInvoke를 사용 하는 함수 포인터 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: 031bda0f93d6a95aa3c774553aefca0647d0518c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400567"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>방법: PInvoke를 사용 하는 함수 포인터 마샬링

이 항목에서는 관리 되는 대리자를 설명 합니다. 관리 되지 않는.NET Framework P/Invoke 기능을 사용 하 여 functions와의 상호 운용 하는 경우 함수 포인터 대신 사용할 수 있습니다. 그러나 Visual C++ 프로그래머는 사용 하는 것이 좋습니다는 C++ Interop 기능 대신 (가능한 경우) P/Invoke는 작은 컴파일 타임 오류를 보고, 형식이 안전한 아니며 구현 되기 번거로울 수를 제공 하기 때문입니다. 관리 되지 않는 API는 DLL로 패키지 하 고 소스 코드를 사용할 수 없는 경우 P/Invoke 유일한 옵션입니다. 그렇지 않은 경우 다음 항목을 참조 합니다.

- [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [방법: C++ Interop를 사용하여 콜백 및 대리자 마샬링](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

관리 되지 않는 Api는 함수 포인터 인수는 네이티브 함수 포인터 대신 관리 되는 대리자를 사용 하 여 관리 되는 코드에서 호출할 수 있습니다. 컴파일러는 자동으로 함수 포인터로 관리 되지 않는 함수에 대리자를 마샬링합니다 하 고 관리/비관리 전환에 필요한 코드를 삽입 합니다.

## <a name="example"></a>예제

다음 코드는 비관리 및 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에는 함수 포인터를 받아들이는 TakesCallback 라는 함수를 정의 하는 DLL입니다. 이 주소는 함수 실행에 사용 됩니다.

관리 되는 모듈을 사용 하 여 네이티브 코드로 함수 포인터로 마샬링됩니다 대리자를 정의 합니다 <xref:System.Runtime.InteropServices.DllImportAttribute> 관리 코드의 네이티브 TakesCallback 함수를 노출 하는 특성입니다. Main 함수에서 대리자 인스턴스에 만들어지고 TakesCallback 함수에 전달 합니다. 프로그램 출력 네이티브 TakesCallback 함수에서이 함수가 실행 되는 하는 방법을 보여 줍니다.

관리 되는 함수 대리자에서 네이티브 함수를 실행 하는 동안.NET Framework 가비지 수집을 방지 하기 위해 관리 되는 대리자에 대 한 가비지 수집을 하지 않습니다.

```cpp
// TraditionalDll5.cpp
// compile with: /LD /EHsc
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   /* Declare an unmanaged function type that takes two int arguments
      Note the use of __stdcall for compatibility with managed code */
   typedef int (__stdcall *CALLBACK)(int);
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);
}

int TakesCallback(CALLBACK fp, int n) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n);
}
```

```cpp
// MarshalDelegate.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

public delegate int GetTheAnswerDelegate(int);
public value struct TraditionalDLL {
   [DllImport("TraditionalDLL5.dll")]
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);
};

int GetNumber(int n) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;
   return x + n;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TraditionalDLL::TakesCallback(fp, 42);
}
```

사용 하 여 기존의 관리 되는 코드에 노출 되지 않습니다 없는 부분 DLL #include 지시문입니다. 사실, DLL은 액세스 런타임에 되므로 문제 함수를 사용 하 여 가져온 <xref:System.Runtime.InteropServices.DllImportAttribute> 컴파일 시 검색 되지 것입니다.

## <a name="see-also"></a>참고자료

[C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
