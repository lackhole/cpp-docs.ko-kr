---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
ms.date: 11/04/2016
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- strxfrm
- _tcsxfrm
- wcsxfrm
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
ms.openlocfilehash: 4e4f5bb6639cbeee0f004f94f09177c08394d43e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258717"
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

로캘별 정보를 기반으로 문자열을 변형합니다.

## <a name="syntax"></a>구문

```C
size_t strxfrm(
   char *strDest,
   const char *strSource,
   size_t count
);
size_t wcsxfrm(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
size_t _strxfrm_l(
   char *strDest,
   const char *strSource,
   size_t count,
   _locale_t locale
);
size_t wcsxfrm_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*strDest*<br/>
대상 문자열입니다.

*strSource*<br/>
소스 문자열입니다.

*count*<br/>
에 배치할 문자의 최대 수 *strDest*합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

종료 null 문자를 세지 않고 변형된 문자열의 길이를 반환합니다. 반환 값 보다 크거나 같은 경우 *개수*, 내용의 *strDest* 는 예측할 수 없습니다. 오류 발생 시 각 함수는 다음과 같이 설정 됩니다. **errno** 반환 **INT_MAX**합니다. 잘못 된 문자에 대 한 **errno** 로 설정 된 **EILSEQ**합니다.

## <a name="remarks"></a>설명

합니다 **strxfrm** 함수에서 가리키는 문자열을 변환 *strSource* 새 폼에 저장 된 데이터 정렬 *strDest*합니다. 개 이하의 *개수* 문자를 null 문자를 포함 하 여 변형 되 고 결과 문자열에 배치 합니다. 로캘의 사용 하 여 변환이 일어납니다 **LC_COLLATE** 범주 설정 합니다. 에 대 한 자세한 **LC_COLLATE**를 참조 하십시오 [setlocale](setlocale-wsetlocale.md)합니다. **strxfrm** 로캘 종속 동작에 현재 로캘을 사용 **_strxfrm_l** 현재 로캘 대신 전달 된 로캘을 사용 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

변환에 대 한 호출 후 **strcmp** 두 가지 변형 된 문자열을 사용 하 여에 대 한 호출의 동일한 결과가 발생 **strcoll** 두 원본 문자열에 적용 합니다. 와 마찬가지로 **strcoll** 하 고 **stricoll**를 **strxfrm** 적절 하 게 멀티 바이트 문자열을 자동으로 처리 합니다.

**wcsxfrm** 의 와이드 문자 버전이 **strxfrm**;의 문자열 인수 **wcsxfrm** 와이드 문자 포인터입니다. 에 대 한 **wcsxfrm**후 문자열 변환에 대 한 호출 **wcscmp** 두 변환 된 문자열을 사용 하 여에 대 한 호출의 동일한 결과가 발생 **wcscoll** 적용할 합니다 두 원본 문자열입니다. **wcsxfrm** 하 고 **strxfrm** 동일 하 게 작동 합니다. **wcsxfrm** 로캘 종속 동작에 현재 로캘을 사용 **_wcsxfrm_l** 현재 로캘 대신 전달 된 로캘을 사용 합니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 *strSource* 가 null 포인터인 경우 또는 *strDest* 은 **NULL** 포인터 (수가 0이 아닌), 이거나 *개수* 보다크면**INT_MAX**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **INT_MAX**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" 로캘에서 문자 집합(ASCII 문자 집합)의 순서는 사전적 문자 순서와 같습니다. 그러나 다른 로캘에서 문자 집합의 문자 순서는 사전적 문자 순서와 다를 수 있습니다. 예를 들어 특정 유럽 로캘의 문자 집합에서 문자 'a'(값 0x61)는 문자 '&\#x00E4;'(값 0xE4) 앞에 오지만 사전적으로는 문자 'ä'가 'a' 앞에 옵니다.

문자 집합과 사전적 문자 순서가 다른 로캘에서 사용 하 여 **strxfrm** 원본 문자열에 차례로 **strcmp** 사전적 문자열을 생성 하는 결과 문자열에서 현재 로캘에 따라 비교 **LC_COLLATE** 범주 설정 합니다. 따라서 위의 로캘에서 사전순으로 두 개의 문자열 비교를 사용 하 여 **strxfrm** 원래 문자열에 대해 **strcmp** 결과 문자열에 있습니다. 또는 사용할 수 있습니다 **strcoll** 대신 **strcmp** 원래 문자열입니다.

**strxfrm** 은 기본적으로 래퍼입니다 [LCMapString](/windows/desktop/api/winnls/nf-winnls-lcmapstringa) 사용 하 여 **LCMAP_SORTKEY**합니다.

다음 식의 값은 저장 하기 위해 필요한 배열의 크기는 **strxfrm** 소스 문자열 중 변환 합니다.

`1 + strxfrm( NULL, string, 0 )`

"C" 로캘에서 **strxfrm** 다음과 같습니다.

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strxfrm**|\<string.h>|
|**wcsxfrm**|\<string.h> 또는 \<wchar.h>|
|**_strxfrm_l**|\<string.h>|
|**_wcsxfrm_l**|\<string.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
