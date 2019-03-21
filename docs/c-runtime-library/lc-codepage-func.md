---
title: ___lc_codepage_func
ms.date: 11/04/2016
apiname:
- ___lc_codepage_func
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
ms.openlocfilehash: aebd978839cc59c94c01e9c24432b69add72c4dc
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751343"
---
# <a name="lccodepagefunc"></a>___lc_codepage_func

내부 CRT 함수입니다. 스레드의 현재 코드 페이지를 검색합니다.

## <a name="syntax"></a>구문

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>반환 값

스레드의 현재 코드 페이지입니다.

## <a name="remarks"></a>주의

`___lc_codepage_func`는 다른 CRT 함수가 CRT 데이터의 스레드 로컬 스토리지에서 현재 코드 페이지를 가져오는 데 사용하는 내부 CRT 함수입니다. [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 함수를 사용하면 이 정보를 사용할 수 있습니다.

*코드 페이지*는 개별 문자에 대한 싱글바이트 또는 더블바이트 코드의 매핑입니다. 여러 코드 페이지에는 일반적으로 언어 또는 언어 그룹에 대해 사용자 지정된 여러 특수 문자가 들어 있습니다. 코드 페이지에 대한 자세한 내용은 [Code Pages](../c-runtime-library/code-pages.md)를 참조하세요.

내부 CRT 함수는 구현과 관련되어 있으며 각 릴리스 시 변경될 수 있습니다. 따라서 사용자 코드에는 사용하지 않는 것이 좋습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>참고 항목

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
