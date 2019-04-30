---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 864236e86b4aeb6ce7b3315df57af1b577693c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267234"
---
# <a name="setcomerrorhandler"></a>_set_com_error_handler

**Microsoft 전용**

COM 오류 처리에 사용되는 기본 함수를 대체합니다.

## <a name="syntax"></a>구문

```
void __stdcall _set_com_error_handler(
   void (__stdcall *pHandler)(
      HRESULT hr,
      IErrorInfo* perrinfo
   )
);
```

#### <a name="parameters"></a>매개 변수

*pHandler*<br/>
대체 함수의 함수 포인터입니다.

*hr*<br/>
HRESULT 정보입니다.

*perrinfo*<br/>
`IErrorInfo` 개체

## <a name="remarks"></a>설명

기본적으로 [_com_raise_error](../cpp/com-raise-error.md)는 모든 COM 오류를 처리합니다. **_set_com_error_handler**를 사용하여 사용자 고유의 오류 처리 함수를 호출하도록 변경할 수 있습니다.

대체 함수에는 `_com_raise_error`와 동일한 시그니처가 있어야 합니다.

## <a name="example"></a>예제

```cpp
// _set_com_error_handler.cpp
// compile with /EHsc
#include <stdio.h>
#include <comdef.h>
#include <comutil.h>

// Importing ado dll to attempt to establish an ado connection.
// Not related to _set_com_error_handler
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")

void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)
{
   throw "Unable to establish the connection!";
}

int main()
{
   _set_com_error_handler(_My_com_raise_error);
   _bstr_t bstrEmpty(L"");
   _ConnectionPtr Connection = NULL;
   try
   {
      Connection.CreateInstance(__uuidof(Connection));
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);
   }
   catch(char* errorMessage)
   {
      printf("Exception raised: %s\n", errorMessage);
   }

   return 0;
}
```

```Output
Exception raised: Unable to establish the connection!
```

## <a name="requirements"></a>요구 사항

**헤더:** \<comdef.h >

**Lib:** 경우는 **/zc: wchar_t** 컴파일러 옵션을 지정 (기본값), comsuppw.lib 또는 comsuppwd.lib를 사용 합니다. 경우는 **/zc: wchar_t-** 컴파일러 옵션을 지정한 경우 comsupp.lib를 사용 합니다. IDE에서이 옵션을 설정 하는 방법을 비롯 한 자세한 내용은 참조 하세요. [/zc: wchar_t (wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)합니다.

## <a name="see-also"></a>참고자료

[컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)
