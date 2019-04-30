---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
ms.date: 11/04/2016
apiname:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
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
apitype: DLLExport
f1_keywords:
- mbsnbicoll
- mbsnbcoll
- mbsnbicoll_l
- _mbsnbcoll
- _mbsnbicoll
- _ftcsnicoll
- _ftcsncoll
- mbsnbcoll_l
helpviewer_keywords:
- _mbsnbcoll_l function
- mbsnbcoll_l function
- _mbsnbcoll function
- _tcsnicoll function
- mbsnbcoll function
- mbsnbicoll_l function
- mbsnbicoll function
- _tcsncoll function
- _mbsnbicoll function
- _mbsnbicoll_l function
- tcsncoll function
- tcsnicoll function
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
ms.openlocfilehash: c18faa3c93969a683b3ee3ef58dd02e1c1ae61f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156722"
---
# <a name="mbsnbcoll-mbsnbcolll-mbsnbicoll-mbsnbicolll"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l

비교 *n* 바이트 멀티 바이트 코드 페이지 정보를 사용 하 여 두 멀티 바이트 문자 문자열입니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _mbsnbcoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
int _mbsnbicoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*string1*, *string2*<br/>
비교할 문자열입니다.

*count*<br/>
비교할 바이트 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

반환 값의 부분 문자열 간 관계를 나타냅니다 *string1* 하 고 *string2*합니다.

|반환 값|설명|
|------------------|-----------------|
|< 0|*string1* 부분 문자열 보다 작거나 *string2* 부분 문자열입니다.|
|0|*string1* substring 동일 *string2* 부분 문자열입니다.|
|> 0|*string1* 부분 문자열 보다 큰 *string2* 부분 문자열입니다.|

경우 *string1* 또는 *string2* 됩니다 **NULL** 또는 *count* 보다 크면 **INT_MAX**, 잘못 된 에 설명 된 대로 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 이러한 함수는 반환 **_NLSCMPERROR** 설정 **errno** 하 **EINVAL**합니다. 사용 하도록 **_NLSCMPERROR**, String.h 또는 Mbstring.h를 포함 합니다.

## <a name="remarks"></a>설명

이러한 각 함수 대조를 첫 번째 *개수* 바이트 *string1* 하 고 *string2* 결과 간의 관계를 나타내는 값을 반환 합니다 부분 *string1* 하 고 *string2*합니다. 경우 부분에서 최종 바이트가 *string1* 하거나 *string2* 선행 바이트 인지 이러한 함수는 부분 문자열의 전체 문자만 비교; 비교에 포함 되지 않습니다. **_mbsnbicoll** 의 대/소문자 버전이 **_mbsnbcoll**합니다. 와 같은 [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) 하 고 [_mbsnbicmp](mbsnbicmp-mbsnbicmp-l.md)를 **_mbsnbcoll** 및 **_mbsnbicoll** 에 따라 두 멀티 바이트 문자 문자열을 비교 합니다 멀티 바이트에 지정 된 사전적 순서 [코드 페이지](../../c-runtime-library/code-pages.md) 에서 현재 사용 합니다.

일부 코드 페이지와 해당 문자 집합의 경우 문자 집합의 문자 순서가 사전적 문자 순서와 다를 수 있습니다. "C" 로캘에서는 해당되지 않습니다. 즉, ASCII 문자 집합에서 문자의 순서는 문자의 사전적 순서와 동일합니다. 예를 들어 특정 유럽 코드 페이지의 문자 집합에서 문자 'a'(값 0x61)는 문자 'ä'(값 0xE4) 앞에 오지만 사전적으로는 문자 'ä'가 'a' 앞에 옵니다. 이러한 상황에서 바이트로 문자열의 사전적 비교를 수행 하려면 사용 **_mbsnbcoll** 대신 **_mbsnbcmp**문자열이 같은지 여부만 확인을 사용 하려면 **_mbsnbcmp**.

때문에 **coll** 함수 반면 사전순으로 비교를 위해 문자열을 비교 합니다 합니다 **cmp** 함수는 문자열이 같은지 여부만 테스트 합니다 **coll** 함수는 해당 하는 보다 훨씬 더 느립니다 **cmp** 버전입니다. 따라서 합니다 **coll** 함수를 현재 코드 페이지에 있는 문자 집합 순서와 사전적 문자 순서 간의 차이 다르며 이러한 차이가 비교에 대 한 관심 있는 경우에 사용 해야 합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 따른 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncoll**|[_strncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll**|[_wcsncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsncoll_l**|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll_l**|[_wcsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsnicoll**|[_strnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll**|[_wcsnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|
|**_tcsnicoll_l**|[_strnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll_l**|[_wcsnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsnbcoll**|\<mbstring.h>|
|**_mbsnbcoll_l**|\<mbstring.h>|
|**_mbsnbicoll**|\<mbstring.h>|
|**_mbsnbicoll_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
