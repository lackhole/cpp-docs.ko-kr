---
title: mbstowcs_s, _mbstowcs_s_l
ms.date: 11/04/2016
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
ms.openlocfilehash: 18af20b5722364ea306daebdcb77f5771d8ea2b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331159"
---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l

멀티바이트 문자 시퀀스를 해당 와이드 문자 시퀀스로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count
);
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
변환된 문자 수입니다.

*wcstr*<br/>
결과로 변환된 와이드 문자열을 위한 버퍼의 주소입니다.

*sizeInWords*<br/>
크기를 *wcstr* 단어 버퍼입니다.

*mbstr*<br/>
null로 끝나는 멀티바이트 문자 시퀀스의 주소입니다.

*count*<br/>
최대 와이드 문자에 저장 합니다 *wcstr* 버퍼, 종결 null을 포함 하지 않습니다 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공시 0, 실패시 오류 코드.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*wcstr* 됩니다 **NULL** 하 고 *sizeInWords* > 0|**EINVAL**|
|*mbstr* 는 **NULL**|**EINVAL**|
|대상 버퍼가 너무 작아서 변환된 된 문자열을 포함할 수 (하지 않는 한 *개수* 됩니다 **_TRUNCATE**; 아래 설명 참조)|**ERANGE**|
|*wcstr* 아닙니다 **NULL** 하 고 *sizeInWords* = = 0|**EINVAL**|

이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 함수 실행을 계속 수 하는 경우 오류 코드를 반환 하 고 설정 **errno** 표에 나와 있는 대로 합니다.

## <a name="remarks"></a>설명

합니다 **mbstowcs_s** 함수에서 가리키는 멀티 바이트 문자의 문자열로 변환 *mbstr* 가리키는 버퍼에 저장 된 와이드 문자로 *wcstr*합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- 멀티바이트 null 문자가 발견되는 경우

- 잘못된 멀티바이트 문자가 발견되는 경우

- 에 저장 된 와이드 문자 수를 *wcstr* equals 버퍼 *개수*합니다.

대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).

경우 *개수* 특수 값인 [_TRUNCATE](../../c-runtime-library/truncate.md), 한 다음 **mbstowcs_s** 만큼 문자열을 최대한 변환 null에 대 한 공간은 남겨 두고 대상 버퍼에 맞지 종결자입니다.

하는 경우 **mbstowcs_s** 소스 문자열을 성공적으로 변환 null 종결자를 포함 하 여 변환된 된 문자열의 와이드 문자에서 크기를 넣습니다  *&#42;pReturnValue* ( 제공*pReturnValue* 아닙니다 **NULL**). 이런 경우에 합니다 *wcstr* 인수가 **NULL** 필요한 버퍼 크기를 결정 하는 방법을 제공 합니다. 경우 *wcstr* 됩니다 **NULL**를 *개수* 무시 됩니다 및 *sizeInWords* 0 이어야 합니다.

하는 경우 **mbstowcs_s** 잘못 된 멀티 바이트 문자가 발견에 0을 배치  *&#42;pReturnValue*대상 버퍼를 빈 문자열로 설정, 설정 **errno** 에 **EILSEQ**를 반환 하 고 **EILSEQ**합니다.

가리키는 시퀀스 하는 경우 *mbstr* 하 고 *wcstr* 겹치는 동작 **mbstowcs_s** 정의 되지 않습니다.

> [!IMPORTANT]
> 되도록 *wcstr* 및 *mbstr* 겹치지 않는 올바르고 *개수* 올바르게 변환할 멀티 바이트 문자의 수를 반영 합니다.

**mbstowcs_s** 모든 로캘 종속 동작에 현재 로캘을 사용 **_mbstowcs_s_l** 대신 전달 된 로캘을 사용 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
