---
title: wctob
ms.date: 11/04/2016
apiname:
- wctob
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
- wctob
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
ms.openlocfilehash: 1d9dca16ca905afbc94d912a8083017ba9cc84e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188534"
---
# <a name="wctob"></a>wctob

와이드 문자가 멀티바이트 문자에 해당하는지 확인하고 해당 멀티바이트 문자 표현을 반환합니다.

## <a name="syntax"></a>구문

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>매개 변수

*wchar*<br/>
변환할 값입니다.

## <a name="return-value"></a>반환 값

하는 경우 **wctob** 성공적으로 변환 와이드 문자를 멀티 바이트 문자의 길이가 정확히 1 바이트 경우에 해당 멀티 바이트 문자 표현을 반환 합니다. 하는 경우 **wctob** 발견 하면 멀티 바이트 문자 또는 멀티 바이트 문자로 변환할 수 없는 와이드 문자는 1 바이트 길이가-1 반환 정확 하 게 합니다.

## <a name="remarks"></a>설명

**wctob** 함수에 포함 된 와이드 문자 변환 *wchar* 를 반환 하 여 전달 된 해당 멀티 바이트 문자로 **int** 값, 멀티 바이트 문자는 길이가 정확히 1 바이트입니다.

하는 경우 **wctob** 성공 하지 하 고 해당 멀티 바이트 문자가 없는 찾을 함수 설정 **errno** 하 **EILSEQ** -1을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램의 동작을 보여 줍니다.는 **wcstombs** 함수입니다.

```C
// crt_wctob.c
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    int     bChar = 0;
    wint_t  wChar = 0;

    // Set the corresponding wide character to exactly one byte.
    wChar = (wint_t)'A';

    bChar = wctob( wChar );
    if (bChar == WEOF)
    {
        printf( "No corresponding multibyte character was found.\n");
    }
    else
    {
        printf( "Determined the corresponding multibyte character to"
                " be \"%c\".\n", bChar);
    }
}
```

```Output
Determined the corresponding multibyte character to be "A".
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
