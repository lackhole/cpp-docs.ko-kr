---
title: '방법: System:: string을 wchar_t * 또는 char * 변환합니다'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- System::String, converting to char or wchar_t
- PtrToStringChars method
- System::String
- wchart type, converting System::String
- char data type, converting System::String to
ms.assetid: 385da01b-5649-4543-8076-e3e251243ff0
ms.openlocfilehash: c9bf8a6af2d48c4b2624b91e2e85f78c63aee6de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387502"
---
# <a name="how-to-convert-systemstring-to-wchart-or-char"></a>방법: System:: string을 wchar_t * 또는 char * 변환합니다

사용할 수 있습니다 `PtrToStringChars` 변환할 Vcclr.h에서 <xref:System.String> 네이티브 `wchar_t *` 또는 `char *`합니다.  이 항상 CLR 문자열은 내부적으로 유니코드 있으므로 와이드 유니코드 문자열 포인터를 반환 합니다. 다음 예제에서와 같이 와이드 문자열에서 변환할 수 있습니다.

## <a name="example"></a>예제

```
// convert_string_to_wchar.cpp
// compile with: /clr
#include < stdio.h >
#include < stdlib.h >
#include < vcclr.h >

using namespace System;

int main() {
   String ^str = "Hello";

   // Pin memory so GC can't move it while native function is called
   pin_ptr<const wchar_t> wch = PtrToStringChars(str);
   printf_s("%S\n", wch);

   // Conversion to char* :
   // Can just convert wchar_t* to char* using one of the
   // conversion functions such as:
   // WideCharToMultiByte()
   // wcstombs_s()
   // ... etc
   size_t convertedChars = 0;
   size_t  sizeInBytes = ((str->Length + 1) * 2);
   errno_t err = 0;
   char    *ch = (char *)malloc(sizeInBytes);

   err = wcstombs_s(&convertedChars,
                    ch, sizeInBytes,
                    wch, sizeInBytes);
   if (err != 0)
      printf_s("wcstombs_s  failed!\n");

    printf_s("%s\n", ch);
}
```

```Output
Hello
Hello
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
