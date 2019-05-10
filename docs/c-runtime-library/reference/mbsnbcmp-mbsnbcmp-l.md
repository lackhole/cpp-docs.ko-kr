---
title: _mbsnbcmp, _mbsnbcmp_l
ms.date: 11/04/2016
apiname:
- _mbsnbcmp
- _mbsnbcmp_l
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
- mbsnbcmp
- tcsnbmp
- _mbsnbcmp_l
- mbsnbcmp_l
- _mbsnbcmp
helpviewer_keywords:
- mbsnbcmp_l function
- mbsnbcmp function
- tcsncmp function
- _mbsnbcmp_l function
- _tcsncmp function
- _mbsnbcmp function
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
ms.openlocfilehash: 4b21fde122f9804633ac037efaf1f343b5cb9440
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285308"
---
# <a name="mbsnbcmp-mbsnbcmpl"></a>_mbsnbcmp, _mbsnbcmp_l

첫 번째 비교 **n** 두 멀티 바이트 문자열의 바이트입니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcmp_l(
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

반환 값의 부분 문자열 간의 서 수 관계를 나타내는 *string1* 하 고 *string2*합니다.

|반환 값|설명|
|------------------|-----------------|
|< 0|*string1* 부분 문자열 보다 작거나 *string2* 부분 문자열입니다.|
|0|*string1* substring 동일 *string2* 부분 문자열입니다.|
|> 0|*string1* 부분 문자열 보다 크면 *string2* 부분 문자열입니다.|

매개 변수 유효성 검사 오류 시 **_mbsnbcmp** 하 고 **_mbsnbcmp_l** 반환 **_NLSCMPERROR**에 정의 된 \<string.h > 및 \< mbstring.h >.

## <a name="remarks"></a>설명

**_mbsnbcmp** 함수는 첫 번째 비교에 가장 *개수* 바이트 *string1* 및 *string2* 나타내는 값을 반환 합니다 부분 문자열 간의 관계입니다. **_mbsnbcmp** 의 대/소문자 구분 버전이 **_mbsnbicmp**합니다. 와 달리 **_mbsnbcoll**하십시오 **_mbsnbcmp** 로캘의 데이터 정렬 순서에 따라 영향을 받지 않습니다. **_mbsnbcmp** 현재 멀티 바이트에 따라 멀티 바이트 문자 시퀀스를 인식 [코드 페이지](../../c-runtime-library/code-pages.md)합니다.

**_mbsnbcmp** 비슷합니다 **_mbsncmp**점을 제외 하 고 **_mbsncmp** 을 바이트가 아닌 문자로 문자열을 비교 합니다.

출력 값에 영향을 받는 합니다 **LC_CTYPE** 후행 바이트 멀티 바이트 문자의 선행 바이트를 지정 하는 로캘의 설정 범주입니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. 합니다 **_mbsnbcmp** 함수가 로캘 종속 동작에 대 한 현재 로캘을 사용 합니다. **_mbsnbcmp_l** 함수를 사용 한다는 점을 제외 하면 동일 합니다 *로캘* 매개 변수 대신 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

이면 *string1* 또는 *string2* 가 null 포인터인 경우 이러한 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우이 함수는 반환 **_NLSCMPERROR** 하 고 **errno** 로 설정 되어 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|---------------------------------------|--------------------|-----------------------|
|**_tcsncmp**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcmp**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|
|**_tcsncmp_l**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcml**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsnbcmp**|\<mbstring.h>|
|**_mbsnbcmp_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mbsnbcmp.c
#include <mbstring.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n          %s\n", string1 );
   printf( "          %s\n\n", string2 );
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );
   result = _mbsncmp( string1, string2 , 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );
   result = _mbsnicmp( string1, string2, 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
}
```

### <a name="output"></a>출력

```Output
Compare strings:
          The quick brown dog jumps over the lazy fox
          The QUICK brown fox jumps over the lazy dog

Function: _mbsnbcmp (first 10 characters only)
Result:   String 1 is greater than string 2

Function: _mbsnicmp _mbsnicmp (first 10 characters only)
Result:   String 1 is equal to string 2
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
