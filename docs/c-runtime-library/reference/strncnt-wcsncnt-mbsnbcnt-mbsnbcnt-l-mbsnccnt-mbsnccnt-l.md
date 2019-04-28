---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
ms.date: 11/04/2016
apiname:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
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
ms.openlocfilehash: 456a11ae98fe8fb40c2ef1d6f4e6d86583f4b7b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209823"
---
# <a name="strncnt-wcsncnt-mbsnbcnt-mbsnbcntl-mbsnccnt-mbsnccntl"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

지정한 개수 내에서 문자 또는 바이트 수를 반환합니다.

> [!IMPORTANT]
> **_mbsnbcnt**, **_mbsnbcnt_l**합니다 **_mbsnccnt**, 및 **_mbsnccnt_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

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
문자 또는에서 검사할 바이트 수가 *str*합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbsnbcnt** 및 **_mbsnbcnt_l** 발견 되는 바이트 수를 반환할 첫 번째에서 *개수* 멀티 바이트 문자의 *str*합니다. **_mbsnccnt** 하 고 **_mbsnccnt_l** 발견 되는 문자 수를 반환할 첫 번째에서 *개수* 의 바이트 *str*. Null 문자를 검사 하기 전에 발생 하는 경우 *str* 에 null 문자 전에 발견 되는 문자 또는 바이트 수가 반환을 완료 합니다. 하는 경우 *str* 보다 작으면 *개수* 문자 또는 바이트 문자열의 문자 또는 바이트 수가 반환 합니다. 하는 경우 *개수* 작으면 0 보다 0을 반환 합니다. 이전 버전에서는 이러한 함수 형식의 반환 값이 있었습니다 **int** 대신 **size_t**합니다.

**_strncnt** 첫 번째에서 문자 수가 반환 *개수* 싱글바이트 문자열의 바이트 *str*합니다. **_wcsncnt** 첫 번째에서 문자 수가 반환 *개수* 와이드 문자 문자열의 와이드 문자 *str*합니다.

## <a name="remarks"></a>설명

**_mbsnbcnt** 하 고 **_mbsnbcnt_l** 발견 되는 바이트 수를 계산 첫 번째에서 *개수* 멀티 바이트 문자의 *str*합니다. **_mbsnbcnt** 하 고 **_mbsnbcnt_l** 대체 **mtob** 대신 사용 해야 **mtob**합니다.

**_mbsnccnt** 하 고 **_mbsnccnt_l** 발견 되는 문자 수를 계산 첫 번째에서 *개수* 바이트 *str*합니다. 하는 경우 **_mbsnccnt** 하 고 **_mbsnccnt_l** 더블 바이트 문자의 두 번째 바이트에 null 문자가 발생 하면 첫 번째 바이트도 null로 간주 됩니다 및 반환 값에 포함 되지 않습니다. **_mbsnccnt** 하 고 **_mbsnccnt_l** 대체 **btom** 대신 사용 해야 **btom**합니다.

하는 경우 *str* 는 **NULL** 포인터 이거나 *count* 가 0 이면 이러한 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md), **errno** 로 설정 되어 **EINVAL**, 함수가 0을 반환 합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 따른 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|루틴에서 반환된 값|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|N/A|
|**_wcsncnt**|N/A|N/A|**_mbsnbcnt**|
|**_wcsncnt**|N/A|N/A|**_mbsnccnt**|
|N/A|N/A|**_mbsnbcnt_l**|**_mbsnccnt_l**|

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
