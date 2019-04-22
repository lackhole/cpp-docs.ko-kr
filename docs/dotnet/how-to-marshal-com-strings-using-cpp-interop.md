---
title: '방법: 사용 하 여 COM 문자열 마샬링 C++ Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: e86cf0b3e57eda9a0f4fa5fe2337d0c42de5669f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780875"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>방법: 사용 하 여 COM 문자열 마샬링 C++ Interop

이 항목에서는 BSTR (COM 프로그래밍에서 선호 하는 기본 문자열 형식) 수 있는 방법을 보여 줍니다. 그 반대로 관리 되지 않는 함수에 관리 되는 전달 합니다. 다른 문자열 형식 상호 작용을 하기 위한 다음 항목을 참조 합니다.

- [방법: C++ Interop를 사용하여 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

다음 코드 예제에서 사용 된 [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md) 구현 #pragma 지시문 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수에서 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 BSTR (COM 프로그래밍에서 사용 하는 문자열 형식)를 전달할 수 있습니다 하는 방법을 보여 줍니다. 관리 되지 않는 함수에 관리 되는 합니다. 호출 함수는 관리 되는 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> 내용의.NET System.String 표현 BSTR의 주소를 가져옵니다. 이 포인터를 사용 하 여 고정 [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) 관리 되지 않는 함수를 실행 하는 동안 해당 실제 주소는 가비지 컬렉션 주기 동안 변경 되지 않도록 확인 합니다. 가비지 수집기가 이동 될 때까지 메모리에서 허용 되지 않습니다 합니다 [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) 범위를 벗어납니다.

```
// MarshalBSTR1.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(BSTR bstr) {
   printf_s("%S", bstr);
}

#pragma managed

int main() {
   String^ s = "test string";

   IntPtr ip = Marshal::StringToBSTR(s);
   BSTR bs = static_cast<BSTR>(ip.ToPointer());
   pin_ptr<BSTR> b = &bs;

   NativeTakesAString( bs );
   Marshal::FreeBSTR(ip);
}
```

## <a name="example"></a>예제

다음 예제에서는 BSTR 전달 하는 방법에서 관리 되지 않는 함수에 관리 되지 않는 합니다. 관리 되는 함수에서 문자열을 BSTR을 사용 하거나 사용 하 여 수신 <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> 변환할를 <xref:System.String> 다른 사용에 대 한 관리 되는 함수입니다. BSTR 나타내는 메모리 관리 되지 않는 힙에서 할당 되므로, 고정 안 함 이므로 필요에 따라 관리 되지 않는 힙의 가비지 컬렉션이 없습니다.

```
// MarshalBSTR2.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedTakesAString(BSTR bstr) {
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);
}

#pragma unmanaged

void UnManagedFunc() {
   BSTR bs = SysAllocString(L"test string");
   printf_s("(unmanaged) passing BSTR to managed func...\n");
   ManagedTakesAString(bs);
}

#pragma managed

int main() {
   UnManagedFunc();
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
