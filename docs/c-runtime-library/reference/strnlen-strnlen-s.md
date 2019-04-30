---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
ms.date: 11/04/2016
apiname:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
ms.openlocfilehash: 960d57ed8c2b1d1dbc6843932b8c76fef35c34a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209672"
---
# <a name="strnlen-strnlens-wcsnlen-wcsnlens-mbsnlen-mbsnlenl-mbstrnlen-mbstrnlenl"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

현재 로캘이나 전달된 로캘을 사용하여 문자열 길이를 가져옵니다. 이러한 함수는 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)의 더 안전한 버전입니다.

> [!IMPORTANT]
> **_mbsnlen**, **_mbsnlen_l**합니다 **_mbstrnlen**, 및 **_mbstrnlen_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t strnlen(
   const char *str,
   size_t numberOfElements
);
size_t strnlen_s(
   const char *str,
   size_t numberOfElements
);
size_t wcsnlen(
   const wchar_t *str,
   size_t numberOfElements
);
size_t wcsnlen_s(
   const wchar_t *str,
   size_t numberOfElements
);
size_t _mbsnlen(
   const unsigned char *str,
   size_t numberOfElements
);
size_t _mbsnlen_l(
   const unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
size_t _mbstrnlen(
   const char *str,
   size_t numberOfElements
);
size_t _mbstrnlen_l(
   const char *str,
   size_t numberOfElements,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
Null 종료 문자열입니다.

*numberOfElements*<br/>
문자열 버퍼의 크기입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

이러한 함수는 null 종결 문자를 제외하고 문자열에 있는 문자의 수를 반환합니다. Null 종결자를 내 첫 번째 경우 *numberOfElements* 문자열의 바이트 (또는 와이드 문자 **wcsnlen**), 한 다음 *numberOfElements* 반환 됩니다 는 오류 조건을 나타냅니다. null로 끝나는 문자열이 엄격 하 게 된 길이 보다 작거나 *numberOfElements*합니다.

**_mbstrnlen** 하 고 **_mbstrnlen_l** 문자열에 잘못 된 멀티 바이트 문자가 포함 된 경우-1을 반환 합니다.

## <a name="remarks"></a>설명

> [!NOTE]
> **strnlen** 에 대 한 대체 기능이 아닙니다 **strlen**; **strnlen** 는 알려진된 버퍼 크기로 들어오는 신뢰할 수 없는 데이터의 크기를 계산 하는 데에 사용 하려는-예를 들어 네트워크 패킷을 합니다. **strnlen** 길이 계산 하지만 문자열이 종료 된 경우 버퍼의 끝까지 진행 하지 않습니다. 다른 상황에서 사용 하 여 **strlen**합니다. (도 마찬가지 **wcsnlen**하십시오 **_mbsnlen**, 및 **_mbstrnlen**.)

이러한 각 함수에 있는 문자의 수를 반환 합니다 *str*null 종결 문자 포함 되지 않습니다. 그러나 **strnlen** 하 고 **strnlen_s** 싱글바이트 문자열로 문자열을 해석 하 고 따라서는 반환 값은 항상 바이트 수와 같은 문자열을 멀티 바이트를 포함 하는 경우에 문자입니다. **wcsnlen** 하 고 **wcsnlen_s** 와이드 문자 버전입니다 **strnlen** 하 고 **strnlen_s** 각각에 대 한 인수 **wcsnlen**  하 고 **wcsnlen_s** 는 와이드 문자 문자열 및 문자 수는 와이드 문자 단위로 합니다. 이 고, 그렇지 **wcsnlen** 하 고 **strnlen** 동일 하 게 동작을 수행 하는 대로 **strnlen_s** 하 고 **wcsnlen_s**합니다.

**strnlen**, **wcsnlen**, 및 **_mbsnlen** 해당 매개 변수를 확인 하지 않습니다. 하는 경우 *str* 됩니다 **NULL**, 액세스 위반이 발생 합니다.

**strnlen_s** 하 고 **wcsnlen_s** 해당 매개 변수 유효성 검사 합니다. 하는 경우 *str* 됩니다 **NULL**, 함수가 0을 반환 합니다.

**_mbstrnlen** 도 해당 매개 변수 유효성을 검사 합니다. 경우 *str* 됩니다 **NULL**, 이거나 *numberOfElements* 보다 크면 **INT_MAX**를 **_mbstrnlen** 에 설명 된 대로 잘못 된 매개 변수 예외를 생성 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **_mbstrnlen** 설정 **errno** 하 **EINVAL** -1을 반환 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen** 하 고 **_mbstrnlen** 멀티 바이트 문자 문자열의 멀티 바이트 문자의 수를 반환 합니다. **_mbsnlen** 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하는 현재 사용 중이거나 전달 되는 로캘에 따라은 멀티 바이트 문자의 유효성에 대 한 테스트 하지 않습니다. **_mbstrnlen** 멀티 바이트 문자의 유효성에 대 한 테스트 및 멀티 바이트 문자 시퀀스를 인식 합니다. 경우에 전달 되는 문자열 **_mbstrnlen** 잘못 된 멀티 바이트 문자가 포함 **errno** 로 설정 되어 **EILSEQ**합니다.

출력 값의 설정이 적용 됩니다는 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 자세한 내용은 합니다. 이러한 함수의 버전은 제외 하 고는 동일가 합니다 **_l** 접미사가 있는 버전이 로캘 종속 동작에 현재 로캘을 사용 합니다 **_l** 접미사 대신 전달 된 로캘 매개 변수를 사용 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strnlen**, **strnlen_s**|\<string.h>|
|**wcsnlen**, **wcsnlen_s**|\<string.h> 또는 \<wchar.h>|
|**_mbsnlen**, **_mbsnlen_l**|\<mbstring.h>|
|**_mbstrnlen**, **_mbstrnlen_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strnlen.c

#include <string.h>

int main()
{
   // str1 is 82 characters long. str2 is 159 characters long

   char* str1 = "The length of a string is the number of characters\n"
               "excluding the terminating null.";
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"
                "than the maximum size specified, the maximum size is\n"
                "returned rather than the actual size of the string.";
   size_t len;
   size_t maxsize = 100;

   len = strnlen(str1, maxsize);
   printf("%s\n Length: %d \n\n", str1, len);

   len = strnlen(str2, maxsize);
   printf("%s\n Length: %d \n", str2, len);
}
```

```Output
The length of a string is the number of characters
excluding the terminating null.
Length: 82

strnlen takes a maximum size. If the string is longer
than the maximum size specified, the maximum size is
returned rather than the actual size of the string.
Length: 100
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
