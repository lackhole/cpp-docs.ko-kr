---
title: wcrtomb
ms.date: 11/04/2016
apiname:
- wcrtomb
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
- wcrtomb
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
ms.openlocfilehash: a5fad3f41c7ed459a1af3fae7c6a5a85c867d5ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188655"
---
# <a name="wcrtomb"></a>wcrtomb

와이드 문자를 멀티바이트 문자 표현으로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [wcrtomb_s](wcrtomb-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t wcrtomb(
   char *mbchar,
   wchar_t wchar,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcrtomb(
   char (&mbchar)[size],
   wchar_t wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*mbchar*<br/>
멀티바이트로 변환된 결과 문자입니다.

*wchar*<br/>
변환할 와이드 문자입니다.

*mbstate*<br/>
에 대 한 포인터를 **mbstate_t** 개체입니다.

## <a name="return-value"></a>반환 값

변환된 멀티바이트 문자를 표시하는 데 필요한 바이트 수를 반환하고, 오류가 발생하면 -1을 반환합니다.

## <a name="remarks"></a>설명

합니다 **wcrtomb** 함수에 포함 된 지정한 변환 상태부터 시작 하 여 와이드 문자를 변환 *mbstate*, 포함 된 값에서 *wchar*에 주소를 나타내는 *mbchar*합니다. 반환 값은 해당 멀티 바이트 문자를 표시 하는 데 필요한 바이트 수를 반환 하지 것입니다 하지만 둘 **MB_CUR_MAX** 바이트입니다.

하는 경우 *mbstate* 이 null 이면 내부 **mbstate_t** 변환 상태가 포함 된 개체 *mbchar* 사용 됩니다. 경우 문자 시퀀스 *wchar* 해당 멀티 바이트 없는 문자 표시를-1이 반환 하며 **errno** 로 설정 되어 **EILSEQ**합니다.

합니다 **wcrtomb** 함수에서 다른 [wctomb, _wctomb_l](wctomb-wctomb-l.md) 해당 다시 시작할 수 있다는입니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어, 응용 프로그램 사용 **wcsrlen** 대신 **wcsnlen**경우에 대 한 후속 호출 **wcsrtombs** 대신 사용한 **wcstombs**.

C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

**wcrtomb** 현재 스레드의 함수가 호출 함수는 다중 스레드 안전 **setlocale** 이 함수가 실행 중인 동안 그리고 합니다 *mbstate* null입니다.

## <a name="example"></a>예제

```C
// crt_wcrtomb.c
// compile with: /W3
// This program converts a wide character
// to its corresponding multibyte character.

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    size_t      sizeOfCovertion = 0;
    mbstate_t   mbstate;
    char        mbStr = 0;
    wchar_t*    wcStr = L"Q";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead
    if (sizeOfCovertion > 0)
    {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wcStr);
        printf(" was converted to the \"%c\" ", mbStr);
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
The corresponding wide character "Q" was converted to the "Q" multibyte character.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
