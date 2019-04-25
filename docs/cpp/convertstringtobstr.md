---
title: ConvertStringToBSTR
ms.date: 11/04/2016
f1_keywords:
- ConvertStringToBSTR
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
ms.openlocfilehash: 5e7d8abd29033fc88dae1e83fcc6467fb0ace46f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154622"
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR

**Microsoft 전용**

`char *` 값을 `BSTR` 형식으로 변환합니다.

## <a name="syntax"></a>구문

```
BSTR __stdcall ConvertStringToBSTR(const char* pSrc)
```

#### <a name="parameters"></a>매개 변수

*pSrc*<br/>
`char *` 변수입니다.

## <a name="example"></a>예제

```cpp
// ConvertStringToBSTR.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")
#pragma comment(lib, "kernel32.lib")

int main() {
   char* lpszText = "Test";
   printf_s("char * text: %s\n", lpszText);

   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);
   wprintf_s(L"BSTR text: %s\n", bstrText);

   SysFreeString(bstrText);
}
```

```Output
char * text: Test
BSTR text: Test
```

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

**헤더:** \<comutil.h >

**Lib:** comsuppw.lib 또는 comsuppwd.lib(자세한 내용은 [/zc: wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조)

## <a name="see-also"></a>참고자료

[컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)