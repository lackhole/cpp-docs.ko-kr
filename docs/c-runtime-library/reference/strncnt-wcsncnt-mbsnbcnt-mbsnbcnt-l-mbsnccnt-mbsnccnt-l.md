---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
ms.date: 11/04/2016
api_name:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcnt
- wcsncnt
- _tcsnbcnt
- _mbsnccnt
- _ftcsnbcnt
- mbsnbcnt
- strncnt
- mbsnbcnt_l
- mbsnccnt_l
- mbsnccnt
- _strncnt
- _wcsncnt
helpviewer_keywords:
- _strncnt function
- _mbsnbcnt function
- _mbsnbcnt_l function
- _mbsnccnt_l function
- mbsnbcnt_l function
- mbsnbcnt function
- tcsnbcnt function
- mbsnccnt_l function
- strncnt function
- _tcsnbcnt function
- mbsnccnt function
- wcsncnt function
- _mbsnccnt function
- _wcsncnt function
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
ms.openlocfilehash: 4c00ae3ff845dfbc3daf4a3ea6ce5c34c43e475f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70947304"
---
# <a name="_strncnt-_wcsncnt-_mbsnbcnt-_mbsnbcnt_l-_mbsnccnt-_mbsnccnt_l"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

지정한 개수 내에서 문자 또는 바이트 수를 반환합니다.

> [!IMPORTANT]
> Windows 런타임에서 실행 되는 응용 프로그램에서는 **_mbsnbcnt**, **_mbsnbcnt_l**, **_mbsnccnt**및 **_mbsnccnt_l** 를 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t _strncnt(
   const char *str,
   size_t count
);
size_t _wcsncnt(
   const wchar_t *str,
   size_t count
);
size_t _mbsnbcnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnbcnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
size_t _mbsnccnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnccnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
검사할 문자열입니다.

*count*<br/>
*Str*에서 검사할 문자 또는 바이트 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbsnbcnt** 및 **_mbsnbcnt_l** 는 *str*의 첫 번째 멀티 바이트 문자 *수* 에 있는 바이트 수를 반환 합니다. **_mbsnccnt** 및 **_mbsnccnt_l** 는 *str* *의 첫 번째 바이트 수에* 있는 문자 수를 반환 합니다. *Str* 검사를 완료 하기 전에 null 문자를 발견 하면 null 문자 앞에 있는 바이트 또는 문자 수를 반환 합니다. *Str* 이 *count* 문자 또는 바이트 미만으로 구성 된 경우 문자열의 문자 또는 바이트 수를 반환 합니다. *Count* 가 0 보다 작은 경우 0을 반환 합니다. 이전 버전에서는 이러한 함수에 **size_t**대신 **int** 형식의 반환 값이 있었습니다.

**_strncnt** 는 싱글바이트 문자열 *str*의 첫 번째 *카운트* 바이트에 있는 문자 수를 반환 합니다. **_wcsncnt** 는 와이드 문자 문자열 *str*의 첫 번째 *개수* 와이드 문자 수를 반환 합니다.

## <a name="remarks"></a>설명

**_mbsnbcnt** 및 **_mbsnbcnt_l** count는 *str*의 첫 번째 멀티 바이트 문자 *수* 에서 발견 된 바이트 수를 계산 합니다. **_mbsnbcnt** 및 **_mbsnbcnt_l** replace **mtob** 는 **mtob**대신 사용 해야 합니다.

**_mbsnccnt** 및 **_mbsnccnt_l** count는 *str* *의 첫 번째 바이트 수에* 있는 문자 수를 계산 합니다. **_Mbsnccnt** 및 **_mbsnccnt_l** 가 더블 바이트 문자의 두 번째 바이트에서 null 문자를 발견 하면 첫 번째 바이트만 null로 간주 되어 반환 되는 count 값에 포함 되지 않습니다. btom 대신 **_mbsnccnt** 및 **_mbsnccnt_l** **replace를** 사용 해야 **합니다.**

*Str* 가 **NULL** 포인터 이거나 *count* 가 0 이면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하 고 **errno** 가 **EINVAL**로 설정 되 고 함수는 0을 반환 합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 따른 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|루틴에서 반환된 값|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|n/a|
|**_wcsncnt**|n/a|n/a|**_mbsnbcnt**|
|**_wcsncnt**|n/a|n/a|**_mbsnccnt**|
|n/a|n/a|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring.h>|
|**_mbsnbcnt_l**|\<mbstring.h>|
|**_mbsnccnt**|\<mbstring.h>|
|**_mbsnccnt_l**|\<mbstring.h>|
|**_strncnt**|\<tchar.h>|
|**_wcsncnt**|\<tchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mbsnbcnt.c

#include  <mbstring.h>
#include  <stdio.h>

int main( void )
{
   unsigned char str[] = "This is a multibyte-character string.";
   unsigned int char_count, byte_count;
   char_count = _mbsnccnt( str, 10 );
   byte_count = _mbsnbcnt( str, 10 );
   if ( byte_count - char_count )
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );
   else
      printf( "The first 10 characters are single-byte.\n");
}
```

### <a name="output"></a>출력

```Output
The first 10 characters are single-byte.
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
