---
title: wcstombs_s, _wcstombs_s_l
ms.date: 11/04/2016
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
ms.openlocfilehash: 6e17fd205d734e94b61d6b80d627a192d9448e29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188560"
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l

와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
Null 종결자를 포함 하 여 변환된 된 문자열의 바이트 크기입니다.

*mbstr*<br/>
결과 변환된 멀티바이트 문자열에 대한 버퍼 주소입니다.

*sizeInBytes*<br/>
크기 (바이트) *mbstr* 버퍼입니다.

*wcstr*<br/>
변환할 와이드 문자열을 가리킵니다.

*count*<br/>
에 저장할 바이트의 최대 수를 *mbstr* 버퍼에 null 종결 문자를 포함 하지 않습니다 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공시 0, 실패시 오류 코드.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*mbstr* 됩니다 **NULL** 하 고 *sizeInBytes* > 0|**EINVAL**|
|*wcstr* 는 **NULL**|**EINVAL**|
|대상 버퍼가 너무 작아서 변환된 된 문자열을 포함할 수 (하지 않는 한 *개수* 됩니다 **_TRUNCATE**; 아래 설명 참조)|**ERANGE**|

이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 함수 실행을 계속 수 하는 경우 오류 코드를 반환 하 고 설정 **errno** 표에 나와 있는 대로 합니다.

## <a name="remarks"></a>설명

합니다 **wcstombs_s** 함수에서 가리키는 와이드 문자의 문자열로 변환 *wcstr* 가리키는 버퍼에 저장 된 멀티 바이트 문자로 *mbstr*합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- null 와이드 문자가 있는 경우

- 변환할 수 없는 와이드 문자가 있는 경우

- 에 저장 된 바이트 수를 *mbstr* equals 버퍼 *개수*합니다.

대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).

경우 *개수* 특수 값인 [_TRUNCATE](../../c-runtime-library/truncate.md), 한 다음 **wcstombs_s** 만큼 문자열을 최대한 변환 null에 대 한 공간은 남겨 두고 대상 버퍼에 맞지 종결자입니다. 반환 값은 문자열 잘리면 **STRUNCATE**, 변환 성공한 것으로 간주 됩니다.

하는 경우 **wcstombs_s** 소스 문자열을 성공적으로 변환에서 null 종결자를 포함 하 여 변환된 된 문자열의 바이트 크기를 넣습니다  *&#42;pReturnValue* (제공  *pReturnValue* 아닙니다 **NULL**). 이런 경우에 합니다 *mbstr* 인수가 **NULL** 필요한 버퍼 크기를 결정 하는 방법을 제공 합니다. 경우 *mbstr* 됩니다 **NULL**에 *개수* 무시 됩니다.

하는 경우 **wcstombs_s** 멀티 바이트 문자를 변환할 수 없는 와이드 문자가에 0을 배치  *&#42;pReturnValue*대상 버퍼를 빈 문자열로 설정, 설정 **errno**  하 **EILSEQ**를 반환 하 고 **EILSEQ**합니다.

가리키는 시퀀스 하는 경우 *wcstr* 하 고 *mbstr* 겹치는 동작 **wcstombs_s** 정의 되지 않습니다.

> [!IMPORTANT]
> 되도록 *wcstr* 및 *mbstr* 겹치지 않는 올바르고 *개수* 올바르게 변환할 와이드 문자 수를 반영 합니다.

**wcstombs_s** 모든 로캘 종속 동작에 현재 로캘을 사용 **_wcstombs_s_l** 동일 **wcstombs** 는 전달 된 로캘을 사용 한다는 점을 제외 하 고 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램의 동작을 보여 줍니다.는 **wcstombs_s** 함수입니다.

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
