---
title: '방법: 사용 하 여 유니코드 문자열 마샬링 C++ Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
ms.openlocfilehash: 37b56834e000cff686557730252f3d425f642772
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400554"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>방법: 사용 하 여 유니코드 문자열 마샬링 C++ Interop

이 항목에서는 시각적 개체의 한 측면을 보여 줍니다. C++ 상호 운용성. 자세한 내용은 [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.

다음 코드 예제에서 사용 된 [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md) 구현 #pragma 지시문 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수에서 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.

이 항목에서는 유니코드 문자열 수 있는 방법을 보여 줍니다. 그 반대로 관리 되지 않는 함수에 관리 되는 전달 합니다. 다른 문자열 형식 상호 작용을 하기 위한 다음 항목을 참조 합니다.

- [방법: C++ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 COM 문자열 마샬링](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example"></a>예제

유니코드 문자열에서 관리 되는 관리 되지 않는 함수에 전달 하려면 (Vcclr.h에서 선언 됨) PtrToStringChars 함수를 사용할 수 있습니다 관리 되는 문자열이 저장 되는 메모리에 액세스 합니다. 네이티브 함수에 전달 되므로이 주소를 반드시 사용 하 여 메모리를 고정 [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) 문자열 데이터를 다시 할당을 방지 하려면 가비지 컬렉션 주기 수행 해야 하는 동안 발생 합니다 관리 되지 않는 함수를 실행합니다.

```
// MarshalUnicode1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const wchar_t* p) {
   printf_s("(native) received '%S'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("test string");
   pin_ptr<const wchar_t> str = PtrToStringChars(s);

   Console::WriteLine("(managed) passing string to native func...");
   NativeTakesAString( str );
}
```

## <a name="example"></a>예제

다음 예제에서는 관리 되는 관리 되지 않는 함수를 호출한 함수에서 유니코드 문자열에 액세스 하는 데 필요한 데이터 마샬링 하는 방법을 보여 줍니다. 네이티브 유니코드 문자열을 수신 하는 관리 되는 함수를 사용 하 여 관리 되는 문자열로 변환 된 <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> 메서드.

```
// MarshalUnicode2.cpp
// compile with: /clr
#include <iostream>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(wchar_t* s) {
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);
   Console::WriteLine("(managed) received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(unmanaged) calling managed func...\n";
   ManagedStringFunc(L"test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
