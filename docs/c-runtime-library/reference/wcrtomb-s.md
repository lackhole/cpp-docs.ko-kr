---
title: wcrtomb_s
ms.date: 11/04/2016
apiname:
- wcrtomb_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: 7fe7fba861eecec562928cf381973f62a4db60fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155474"
---
# <a name="wcrtombs"></a>wcrtomb_s

와이드 문자를 멀티바이트 문자 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcrtomb](wcrtomb.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
기록된 바이트 수를 반환하거나, 오류가 발생하면 -1을 반환합니다.

*mbchar*<br/>
멀티바이트로 변환된 결과 문자입니다.

*sizeOfmbchar*<br/>
크기를 *mbchar* 변수 (바이트)에서입니다.

*wchar*<br/>
변환할 와이드 문자입니다.

*mbstate*<br/>
에 대 한 포인터를 **mbstate_t** 개체입니다.

## <a name="return-value"></a>반환 값

0 반환 합니다 요소나 **errno** 값에 오류가 발생 합니다.

## <a name="remarks"></a>설명

합니다 **wcrtomb_s** 함수에 포함 된 지정한 변환 상태부터 시작 하 여 와이드 문자를 변환 *mbstate*, 포함 된 값에서 *wchar*에 주소를 나타내는 *mbchar*합니다. 합니다 *pReturnValue* 값 이지만 변환 된 바이트의 수 둘 **MB_CUR_MAX** 바이트 또는 오류가 발생 한 경우에-1입니다.

하는 경우 *mbstate* 이 null 이면 내부 **mbstate_t** 변환 상태가 사용 됩니다. 문자에 포함 된 경우 *wchar* 를 해당 멀티 바이트 문자 값이 없는 *pReturnValue* -1이 됩니다 및 함수는 반환 된 **errno** 값 **EILSEQ**합니다.

합니다 **wcrtomb_s** 함수에서 다른 [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md) 해당 다시 시작할 수 있다는입니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어, 응용 프로그램 사용 **wcsrlen** 대신 **wcslen**경우에 대 한 후속 호출 **wcsrtombs_s** 대신 사용한 **wcstombs_s**.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 간편하게 사용할 수 있습니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

**wcrtomb_s** 현재 스레드의 함수가 호출 함수는 다중 스레드 안전 **setlocale** 이 함수가 실행 중인 동안 하며 *mbstate* null입니다.

## <a name="example"></a>예제

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
