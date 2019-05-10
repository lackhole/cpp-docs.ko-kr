---
title: _isctype, iswctype, _isctype_l, _iswctype_l
ms.date: 11/04/2016
apiname:
- _isctype_l
- iswctype
- _iswctype_l
- _isctype
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswctype
- _isctype
- _isctype_l
- _iswctype
- isctype
- iswctype_l
- isctype_l
- _iswctype_l
helpviewer_keywords:
- isctype_l function
- iswctype_l function
- iswctype function
- _isctype function
- _isctype_l function
- _iswctype_l function
- isctype function
- _iswctype function
ms.assetid: cf7509b7-12fc-4d95-8140-ad2eb98173d3
ms.openlocfilehash: c5eb0b51cf0371100ed884221ee04885dfbe9ad9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157320"
---
# <a name="isctype-iswctype-isctypel-iswctypel"></a>_isctype, iswctype, _isctype_l, _iswctype_l

테스트 *c* 하 여 지정 된 ctype 속성을 *desc* 인수입니다. 유효한 각 값에 대 한 *desc*, 하는 해당 와이드 문자 분류 루틴이 있습니다.

## <a name="syntax"></a>구문

```C
int _isctype(
   int c,
   _ctype_t desc
);
int _isctype_l(
   int c,
   _ctype_t desc,
   _locale_t locale
);
int iswctype(
   wint_t c,
   wctype_t desc
);
int _iswctype_l(
   wint_t c,
   wctype_t desc,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*desc*<br/>
테스트할 속성입니다. 일반적으로 ctype 또는 [wctype](wctype.md)를 사용하여 검색됩니다.

*locale*<br/>
모든 로캘 종속 테스트에 사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_isctype** 하 고 **iswctype** 경우 0이 아닌 값을 반환 *c* 로 지정 된 속성이 *desc* 현재 로캘 또는 그렇지 않은 경우에 0에서. 포함 된 이러한 함수의 버전을 **_l** 접미사는 로캘 종속 동작에 현재 로캘 대신 전달 된 로캘을 사용 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

동작 **_isctype** 하 고 **_isctype_l** 경우 정의 되지 않습니다 *c* EOF가 범위인 0부터 0xff까지 포괄 합니다. 디버그 CRT 라이브러리가 사용 되는 경우 및 *c* 함수 raise 이러한 값 중 하나가 아닌 한 어설션입니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|N/A|**_isctype**|N/A|**_iswctype**|
|N/A|**_isctype_l**|N/A|**_iswctype_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_isctype**|\<ctype.h>|
|**iswctype**|\<ctype.h> 또는 \<wchar.h>|
|**_isctype_l**|\<ctype.h>|
|**_iswctype_l**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
