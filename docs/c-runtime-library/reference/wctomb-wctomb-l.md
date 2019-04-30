---
title: wctomb, _wctomb_l
ms.date: 11/04/2016
apiname:
- _wctomb_l
- wctomb
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wctomb
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
ms.openlocfilehash: df0abdd644027f9bab8cd177dfd4d0af4c98df35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188547"
---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l

와이드 문자를 해당 멀티바이트 문자로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int wctomb(
   char *mbchar,
   wchar_t wchar
);
int _wctomb_l(
   char *mbchar,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*mbchar*<br/>
멀티바이트 문자의 주소입니다.

*wchar*<br/>
와이드 문자입니다.

## <a name="return-value"></a>반환 값

하는 경우 **wctomb** 와이드 문자 변환 멀티 바이트 문자를 바이트 수를 반환 (초과 하지 않는 것 **MB_CUR_MAX**) 와이드 문자에서. 하는 경우 *wchar* 와이드 문자 null 문자 (L'\ \0')은 **wctomb** 1을 반환 합니다. 하는 경우 대상 포인터 *mbchar* 됩니다 **NULL**합니다 **wctomb** 0을 반환 합니다. 현재 로캘에서 변환이 불가능 **wctomb** -1을 반환 하 고 **errno** 로 설정 되어 **EILSEQ**합니다.

## <a name="remarks"></a>설명

합니다 **wctomb** 변환 함수 해당 *wchar* 인수를 해당 멀티 바이트 문자로의 결과 가져와 *mbchar*합니다. 모든 프로그램에서 언제든지 이 함수를 호출할 수 있습니다. **wctomb** 모든 로캘 종속 동작에 현재 로캘을 사용 **_wctomb_l** 동일 **wctomb** 는 전달 된 로캘을 사용 한다는 점을 제외 하 고 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**wctomb** 해당 매개 변수 유효성을 검사 합니다. 하는 경우 *mbchar* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수-1을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wctomb**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램은 wctomb 함수의 동작을 보여 줍니다.

```cpp
// crt_wctomb.cpp
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int i;
   wchar_t wc = L'a';
   char *pmb = (char *)malloc( MB_CUR_MAX );

   printf( "Convert a wide character:\n" );
   i = wctomb( pmb, wc ); // C4996
   // Note: wctomb is deprecated; consider using wctomb_s
   printf( "   Characters converted: %u\n", i );
   printf( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
