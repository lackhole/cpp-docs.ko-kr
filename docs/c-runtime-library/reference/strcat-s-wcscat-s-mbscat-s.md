---
title: strcat_s, wcscat_s, _mbscat_s, _mbscat_s_l
ms.date: 01/22/2019
apiname:
- strcat_s
- _mbscat_s
- _mbscat_s_l
- wcscat_s
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
- strcat_s
- wcscat_s
- _mbscat_s
- _mbscat_s_l
helpviewer_keywords:
- wcscat_s function
- strcat_s function
- mbscat_s function
- strings [C++], appending
- _mbscat_s function
- _mbscat_s_l function
- appending strings
ms.assetid: 0f2f9901-c5c5-480b-98bc-f8f690792fc0
ms.openlocfilehash: bd7894ba77e7fa67fa3844587394bd3e2e821391
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354381"
---
# <a name="strcats-wcscats-mbscats-mbscatsl"></a>strcat_s, wcscat_s, _mbscat_s, _mbscat_s_l

문자열을 추가합니다. 이러한 버전의 [strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> **_mbscat_s** 하 고 **_mbscat_s_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t strcat_s(
   char *strDestination,
   size_t numberOfElements,
   const char *strSource
);
errno_t wcscat_s(
   wchar_t *strDestination,
   size_t numberOfElements,
   const wchar_t *strSource
);
errno_t _mbscat_s(
   unsigned char *strDestination,
   size_t numberOfElements,
   const unsigned char *strSource
);
errno_t _mbscat_s_l(
   unsigned char *strDestination,
   size_t numberOfElements,
   const unsigned char *strSource,
   _locale_t locale
);
template <size_t size>
errno_t strcat_s(
   char (&strDestination)[size],
   const char *strSource
); // C++ only
template <size_t size>
errno_t wcscat_s(
   wchar_t (&strDestination)[size],
   const wchar_t *strSource
); // C++ only
template <size_t size>
errno_t _mbscat_s(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource
); // C++ only
template <size_t size>
errno_t _mbscat_s_l(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*strDestination*<br/>
Null 종료 대상 문자열 버퍼입니다.

*numberOfElements*<br/>
대상 문자열 버퍼의 크기입니다.

*strSource*<br/>
null 종료 소스 문자열 버퍼입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공 시 0이고, 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|*strDestination*|*numberOfElements*|*strSource*|반환 값|내용을 *strDestination*|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL** 또는 종료 되지 않음|any|any|**EINVAL**|수정 안 됨|
|any|any|**NULL**|**EINVAL**|*strDestination*0 [0] 집합|
|any|0 또는 너무 작음|any|**ERANGE**|*strDestination*0 [0] 집합|

## <a name="remarks"></a>설명

합니다 **strcat_s** 함수를 추가 *strSource* 하 *strDestination* 하 고 결과 문자열을 null 문자로 종료 됩니다. 첫 문자의 *strSource* 의 종료 null 문자를 덮어씁니다 *strDestination*합니다. 동작은 **strcat_s** 소스 문자열과 대상 문자열이 겹치는 경우 정의 되지 않습니다.

두 번째 매개 변수는 버퍼의 나머지 크기가 아닌 전체 크기입니다.

```C
char buf[16];
strcpy_s(buf, 16, "Start");
strcat_s(buf, 16, " End");               // Correct
strcat_s(buf, 16 - strlen(buf), " End"); // Incorrect
```

**wcscat_s** 하 고 **_mbscat_s** 와이드 문자 및 멀티 바이트 문자 버전입니다 **strcat_s**합니다. 인수 및 반환 값 **wcscat_s** 은 와이드 문자열이 고 **_mbscat_s** 는 멀티 바이트 문자 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

경우 *strDestination* null 포인터 이거나 null로 종료 되지 이거나 *strSource* 되는 **NULL** 포인터 대상 문자열이 너무 작은 경우 또는 잘못 된 매개 변수 에 설명 된 대로 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 이러한 함수는 반환 **EINVAL** 설정 **errno** 하 **EINVAL**합니다.

함수의 버전은 **_l** 접미사 동일 하 게 동작에 현재 로캘 대신 전달 된 로캘 매개 변수를 사용 하 여 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscat_s**|**strcat_s**|**_mbscat_s**|**wcscat_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strcat_s**|\<string.h>|
|**wcscat_s**|\<string.h> 또는 \<wchar.h>|
|**_mbscat_s**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)의 코드 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
