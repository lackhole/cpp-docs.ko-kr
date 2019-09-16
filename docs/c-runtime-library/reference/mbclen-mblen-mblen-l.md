---
title: _mbclen, mblen, _mblen_l, _mbclen_l
ms.date: 01/22/2019
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mblen
- ftclen
- _mbclen
- _mbclen_l
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- _mbclen_l function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: 96775f513b33eb407981480c17cb609dd85383f6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952571"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen, mblen, _mblen_l, _mbclen_l

멀티바이트 문자의 길이를 가져오고 유효성을 확인합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t _mbclen(
   const unsigned char *c
);
size_t _mbclen_l(
   unsigned char const* c,
   _locale_t locale
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
멀티바이트 문자입니다.

*mbstr*<br/>
멀티바이트 문자 바이트 시퀀스의 주소입니다.

*count*<br/>
검사할 바이트 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbclen** 는 멀티 바이트 문자 *c* 가 1 또는 2 바이트 길이에 따라 1 또는 2를 반환 합니다. **_Mbclen**에 대 한 오류 반환은 없습니다. *Mbstr* 이 **NULL**이 아닌 경우 **mblen** 는 멀티 바이트 문자의 길이 (바이트)를 반환 합니다. *Mbstr* 가 **null** 이거나 와이드 문자 null 문자를 가리키는 경우 **mblen** 는 0을 반환 합니다. *Mbstr* 가 가리키는 개체가 첫 번째 *카운트* 문자 내에서 유효한 멀티 바이트 문자를 구성 하지 않는 경우 **mblen** 는-1을 반환 합니다.

## <a name="remarks"></a>설명

**_Mbclen** 함수는 멀티 바이트 문자 *c*의 길이 (바이트)를 반환 합니다. *C* 가 **_ismbblead**에 대 한 암시적 호출에 의해 결정 된 멀티 바이트 문자의 선행 바이트를 가리키지 않는 경우 **_mbclen** 의 결과를 예측할 수 없습니다.

**mblen** 은 유효한 멀티 바이트 문자인 경우 *mbstr* 의 길이 (바이트)를 반환 하 고 코드 페이지와 관련 된 멀티 바이트 문자 유효성을 확인 합니다. **mblen** 은 *mbstr*에 포함 되었지만 **MB_CUR_MAX** 바이트를 초과 하지 않는 바이트 *수* 를 검사 합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md) 을 참조 하세요. **_L** 접미사가 없는 이러한 함수 버전은이 로캘 종속 동작에 현재 로캘을 사용 합니다. **_L** 접미사로 이루어진 버전은 동일 하 게 동작 하지만 대신 전달 된 로캘 매개 변수를 사용 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|매크로 또는 인라인 함수에 매핑|**_mbclen**|매크로 또는 인라인 함수에 매핑|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
