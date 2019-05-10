---
title: strncmp, wcsncmp, _mbsncmp, _mbsncmp_l
ms.date: 11/04/2016
apiname:
- strncmp
- _mbsncmp
- wcsncmp
- _mbsncmp_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _ftcsnccmp
- _ftcsncmp
- _tcsncmp
- _tcsnccmp
- strncmp
- _mbsncmp
- wcsncmp
helpviewer_keywords:
- _tcsnccmp function
- ftcsncmp function
- wcsncmp function
- _ftcsncmp function
- _mbsncmp function
- tcsncmp function
- mbsncmp function
- _mbsncmp_l function
- mbsncmp_l function
- strncmp function
- strings [C++], comparing characters of
- string comparison [C++], strncmp function
- _tcsncmp function
- tcsnccmp function
- ftcsnccmp function
- characters [C++], comparing
- _ftcsnccmp function
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
ms.openlocfilehash: 8f022dec6c161814ade5c6be5aaccfcd239a4af4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209861"
---
# <a name="strncmp-wcsncmp-mbsncmp-mbsncmpl"></a>strncmp, wcsncmp, _mbsncmp, _mbsncmp_l

두 문자열의 문자를 지정한 수까지 비교합니다.

> [!IMPORTANT]
> **_mbsncmp** 하 고 **_mbsncmp_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int strncmp(
   const char *string1,
   const char *string2,
   size_t count
);
int wcsncmp(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count
);
int _mbsncmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsncmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>매개 변수

*string1*, *string2*<br/>
비교할 문자열입니다.

*count*<br/>
비교할 문자 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

반환 값의 부분 문자열 간 관계를 나타냅니다 *string1* 하 고 *string2* 다음과 같습니다.

|반환 값|설명|
|------------------|-----------------|
|< 0|*string1* 부분 문자열 보다 작거나 *string2* 부분 문자열|
|0|*string1* substring 동일 *string2* 부분 문자열|
|> 0|*string1* 부분 문자열 보다 큰 *string2* 부분 문자열|

매개 변수 유효성 검사 오류 시 **_mbsncmp** 하 고 **_mbsncmp_l** 반환 **_NLSCMPERROR**에 정의 된 \<string.h > 및 \< mbstring.h >.

## <a name="remarks"></a>설명

합니다 **strncmp** 최대 첫 번째 서 수 비교를 수행 하는 함수 *개수* 자 *string1* 및 *string2* 및 부분 문자열 간의 관계를 나타내는 값을 반환 합니다. **strncmp** 의 대/소문자 구분 버전이 **_strnicmp**합니다. **wcsncmp** 하 고 **_mbsncmp** 버전의 대/소문자 구분 **_wcsnicmp** 하 고 **_mbsnicmp**합니다.

**wcsncmp** 하 고 **_mbsncmp** 와이드 문자 및 멀티 바이트 문자 버전입니다 **strncmp**합니다. 인수 **wcsncmp** 은 와이드 문자열이 고 **_mbsncmp** 는 멀티 바이트 문자 문자열입니다. **_mbsncmp** 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하며 반환 **_NLSCMPERROR** 오류 발생 시.

또한 **_mbsncmp** 하 고 **_mbsncmp_l** 매개 변수 유효성 검사 합니다. 하는 경우 *string1* 하거나 *string2* 가 null 포인터인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **_mbsncmp** 하 고 **_mbsncmp_l** 반환 **_NLSCMPERROR** 설정 하 고 **errno** 에  **EINVAL**합니다. **strncmp** 하 고 **wcsncmp** 해당 매개 변수를 확인 하지 않습니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

비교 동작에 **_mbsncmp** 하 고 **_mbsncmp_l** 설정의 영향을 받는 합니다 **LC_CTYPE** 로캘 범주 설정 합니다. 이 설정은 멀티바이트 문자의 선행 및 후행 바이트 검색을 제어합니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. 합니다 **_mbsncmp** 함수가 로캘 종속 동작에 대 한 현재 로캘을 사용 합니다. **_mbsncmp_l** 함수를 사용 한다는 점을 제외 하면 동일 합니다 *로캘* 매개 변수 대신 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요. 로캘이 싱글바이트 로캘의 경우 이러한 함수의 동작이 동일 **strncmp**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccmp**|**strncmp**|**_mbsncmp**|**wcsncmp**|
|**_tcsncmp**|**strncmp**|**_mbsnbcmp**|**wcsncmp**|
|**_tccmp**|매크로 또는 인라인 함수에 매핑|**_mbsncmp**|매크로 또는 인라인 함수에 매핑|
|**해당 없음**|**해당 없음**|**_mbsncmp_l**|**해당 없음**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strncmp**|\<string.h>|
|**wcsncmp**|\<string.h> 또는 \<wchar.h>|
|**_mbsncmp**, **_mbsncmp_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strncmp.c
#include <string.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n      %s\n      %s\n\n",
           string1, string2 );
   printf( "Function:   strncmp (first 10 characters only)\n" );
   result = strncmp( string1, string2 , 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n\n", tmp );
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );
   result = _strnicmp( string1, string2, 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
      The quick brown dog jumps over the lazy fox
      The QUICK brown fox jumps over the lazy dog

Function:   strncmp (first 10 characters only)
Result:      String 1 is greater than string 2

Function:   strnicmp _strnicmp (first 10 characters only)
Result:      String 1 is equal to string 2
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
