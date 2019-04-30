---
title: _stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l
ms.date: 11/04/2016
apiname:
- _mbsicoll_l
- _stricoll_l
- _mbsicoll
- _wcsicoll_l
- _wcsicoll
- _stricoll
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- stricoll
- _stricoll
- _wcsicoll
- mbsicoll_l
- _mbsicoll
- _ftcsicoll
- wcsicoll_l
- _tcsicoll
- mbsicoll
- stricoll_l
helpviewer_keywords:
- code pages, using for string comparisons
- _ftcsicoll function
- _mbsicoll_l function
- _mbsicoll function
- mbsicoll function
- stricoll function
- tcsicoll function
- string comparison [C++], culture-specific
- _tcsicoll function
- _stricoll function
- _stricoll_l function
- _wcsicoll function
- mbsicoll_l function
- stricoll_l function
- strings [C++], comparing by code page
- ftcsicoll function
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
ms.openlocfilehash: bd2406751fd2855afd02743c98938e530398e7d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353666"
---
# <a name="stricoll-wcsicoll-mbsicoll-stricolll-wcsicolll-mbsicolll"></a>_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l

로캘별 정보를 사용하여 문자열을 비교합니다.

> [!IMPORTANT]
> **_mbsicoll** 하 고 **_mbsicoll_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _stricoll(
   const char *string1,
   const char *string2
);
int _wcsicoll(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicoll(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricoll_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicoll_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*string1*, *string2*<br/>
비교할 Null 종료 문자열입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수의 관계를 나타내는 값을 반환 *string1* 하 *string2*다음과 같이 합니다.

|반환 값|문자열 1과 문자열 2의 관계|
|------------------|----------------------------------------|
|< 0|*string1* 보다 작거나 *string2*|
|0|*string1* 동일 *string2*|
|> 0|*string1* 보다 큰 *string2*|
|**_NLSCMPERROR**|오류가 발생했습니다.|

이러한 각 함수 반환 **_NLSCMPERROR**합니다. 사용 하도록 **_NLSCMPERROR**에 포함 되어 \<string.h > 또는 \<mbstring.h >. **_wcsicoll** 경우 실패할 수 있습니다 *string1* 하거나 *string2* 도메인 외부의 데이터 정렬 시퀀스의 와이드 문자 코드가 포함 되어 있습니다. 오류가 발생 하는 경우 **_wcsicoll** 설정할 수 있습니다 **errno** 하 **EINVAL**합니다. 에 대 한 호출에서 오류를 확인 하려면 **_wcsicoll**설정 **errno** 0으로 확인 한 다음 **errno** 호출한 후 **_wcsicoll**합니다.

## <a name="remarks"></a>설명

이러한 각 함수는 대/소문자 구분 비교를 수행 *string1* 하 고 *string2* 에서 현재 사용 중인 코드 페이지에 따라 합니다. 현재 코드 페이지에서 문자 집합 순서와 사전적 문자 순서가 다르며 이러한 차이가 문자열 비교 시 중요한 경우에만 이러한 함수를 사용해야 합니다.

**_stricmp** 에서 서로 다릅니다 **_stricoll** 에 **_stricmp** 영향을 비교 **LC_CTYPE**반면는 **_stricoll** 비교에 따라 합니다 **LC_CTYPE** 하 고 **LC_COLLATE** 로캘 범주입니다. 대 한 자세한 내용은 합니다 **LC_COLLATE** 범주를 참조 하세요 [setlocale](setlocale-wsetlocale.md) 및 [로캘 범주](../../c-runtime-library/locale-categories.md)합니다. 없는 이러한 함수 버전을 **_l** 사용 하 여 접미사 현재 로캘을; 버전을 사용 하 여는 **_l** 접미사는 전달 된 로캘을 사용 한다는 점을 제외 하면 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 이면 *string1* 하거나 *string2* 됩니다 **NULL** 에 설명 된 대로 포인터를 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md). 실행을 계속 하도록 허용 된 경우 이러한 함수는 반환 **_NLSCMPERROR** 설정 **errno** 하 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicoll**|**_stricoll**|**_mbsicoll**|**_wcsicoll**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_stricoll**, **_stricoll_l**|\<string.h>|
|**_wcsicoll**, **_wcsicoll_l**|\<wchar.h>, \<string.h>|
|**_mbsicoll**, **_mbsicoll_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[로캘](../../c-runtime-library/locale.md)<br/>
[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
