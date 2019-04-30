---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 11/04/2016
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
ms.openlocfilehash: d27b2128d79d7ff3ab0150e182d494fed52d46ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353841"
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

대소문자를 구분하지 않는 문자열 비교를 수행합니다.

> [!IMPORTANT]
> **_mbsicmp** 하 고 **_mbsicmp_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _stricmp(
   const char *string1,
   const char *string2
);
int _wcsicmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricmp_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicmp_l(
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

반환 값의 관계를 나타냅니다 *string1* 하 *string2* 다음과 같습니다.

|반환 값|설명|
|------------------|-----------------|
|< 0|*string1* 보다 작거나 *string2*|
|0|*string1* 동일 *string2*|
|> 0|*string1* 보다 큰 *string2*|

오류 발생 시 **_mbsicmp** 반환 **_NLSCMPERROR**에 정의 된 \<string.h > 및 \<mbstring.h >.

## <a name="remarks"></a>설명

**_stricmp** 함수 서 수로 비교 *string1* 하 고 *string2* 관계를 나타내는 값을 각 문자를 소문자로 반환 변환한 후 합니다. **_stricmp** 에서 서로 다릅니다 **_stricoll** 에 **_stricmp** 비교만 영향을 받는 **LC_CTYPE**를 나타내는 문자는 위 결정 하는 및 소문자입니다. 합니다 **_stricoll** 둘 다에 따라 문자열을 비교 하는 함수는 **LC_CTYPE** 하 고 **LC_COLLATE** 로캘의 데이터 정렬 및 대/소문자를 포함 하는 범주 순서입니다. 에 대 한 자세한 내용은 합니다 **LC_COLLATE** 범주를 참조 하세요 [setlocale](setlocale-wsetlocale.md) 및 [로캘 범주](../../c-runtime-library/locale-categories.md)합니다. 없는 이러한 함수의 버전은 **_l** 접미사는 로캘 종속 동작에 대 한 현재 로캘을 사용 합니다. 접미사가 있는 버전은 전달된 로캘을 사용한다는 점만 제외하면 동일합니다. 로캘이 설정되지 않은 경우에는 C 로캘이 사용됩니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

> [!NOTE]
> **_stricmp** 같습니다 **_strcmpi**합니다. 서로 교환해 서 사용할 수 있지만 **_stricmp** 는 기본 표준입니다.

합니다 **_strcmpi** 함수는 동일 **_stricmp** 하며 이전 버전과 호환성을 위해서만 제공 됩니다.

때문에 **_stricmp** 소문자 비교를 수행 예기치 않은 동작이 발생할 수 있습니다.

경우 대 소문자 변환이 **_stricmp** 결과 영향을 비교, JOHNSTON과 JOHN_HENRY 두 문자열이 있다고 가정 합니다. JOHN_HENRY 문자열은 "_"의 ASCII 값이 소문자 S보다 작기 때문에 JOHNSTON보다 작은 것으로 간주됩니다. 실제로 ASCII 값이 91~96인 문자는 모든 문자보다 작은 것으로 간주됩니다.

경우는 [strcmp](strcmp-wcscmp-mbscmp.md) 함수를 대신 사용 됩니다 **_stricmp**, JOHN_HENRY가 JOHNSTON 보다 커야 합니다.

**_wcsicmp** 하 고 **_mbsicmp** 와이드 문자 및 멀티 바이트 문자 버전입니다 **_stricmp**합니다. 인수 및 반환 값 **_wcsicmp** 은 와이드 문자열이 고 **_mbsicmp** 는 멀티 바이트 문자 문자열입니다. **_mbsicmp** 현재 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하 고 반환 **_NLSCMPERROR** 오류 발생 시. 자세한 내용은 [코드 페이지](../../c-runtime-library/code-pages.md) 참조하세요. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

**_wcsicmp** 하 고 **wcscmp** 점을 제외 하면 동일 하 게 작동 **wcscmp** 해당 인수를 비교 하기 전에 소문자로 변환 하지 않습니다. **_mbsicmp** 하 고 **_mbscmp** 점을 제외 하면 동일 하 게 작동 **_mbscmp** 해당 인수를 비교 하기 전에 소문자로 변환 하지 않습니다.

호출 해야 합니다 [setlocale](setlocale-wsetlocale.md) 에 대 한 **_wcsicmp** 라틴 1 문자를 사용 하 여 작동 합니다. 기본적으로는 C 로캘이 적용되므로 예를 들어 ä와 Ä는 비교 시 같은 항목으로 간주되지 않습니다. 호출 **setlocale** 호출 하기 전에 C 이외의 모든 로캘 **_wcsicmp**합니다. 다음 예제에서는 어떻게 **_wcsicmp** 로캘을 구분 하는:

```C
// crt_stricmp_locale.c
#include <string.h>
#include <stdio.h>
#include <locale.h>

int main() {
   setlocale(LC_ALL,"C");   // in effect by default
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails
   setlocale(LC_ALL,"");
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds
}
```

호출 하는 대안 [_create_locale, _wcreate_locale](create-locale-wcreate-locale.md) 반환 된 로캘 개체에 대 한 매개 변수로 전달 **_wcsicmp_l**합니다.

이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 이면 *string1* 하거나 *string2* 가 null 포인터인에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 실행을 계속 하도록 허용 된 경우 이러한 함수는 반환 **_NLSCMPERROR** 설정 **errno** 하 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<string.h>|
|**_wcsicmp**, **_wcsicmp_l**|\<string.h> 또는 \<wchar.h>|
|**_mbsicmp**, **_mbsicmp_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_stricmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
