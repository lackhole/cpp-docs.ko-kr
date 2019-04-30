---
title: wcsrtombs_s
ms.date: 11/04/2016
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: bd965271a65fa91b427c7af7bbd4173b129e1d8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188573"
---
# <a name="wcsrtombss"></a>wcsrtombs_s

와이드 문자열을 멀티바이트 문자열 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcsrtombs](wcsrtombs.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
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
에 저장 될 바이트의 최대 수를 *mbstr* 버퍼 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)합니다.

*mbstate*<br/>
에 대 한 포인터를 **mbstate_t** 변환 상태 개체입니다.

## <a name="return-value"></a>반환 값

성공시 0, 실패시 오류 코드.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*mbstr* 됩니다 **NULL** 하 고 *sizeInBytes* > 0|**EINVAL**|
|*wcstr* 는 **NULL**|**EINVAL**|
|대상 버퍼가 너무 작아서 변환된 된 문자열을 포함할 수 (하지 않는 한 *개수* 됩니다 **_TRUNCATE**; 아래 설명 참조)|**ERANGE**|

이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 함수 실행을 계속 수 하는 경우 오류 코드를 반환 하 고 설정 **errno** 표에 나와 있는 대로 합니다.

## <a name="remarks"></a>설명

합니다 **wcsrtombs_s** 함수에서 가리키는 와이드 문자의 문자열로 변환 *wcstr* 가리키는 버퍼에 저장 된 멀티 바이트 문자로 *mbstr*를 사용 하 여는 에 포함 된 변환 상태 *mbstate*합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- null 와이드 문자가 있는 경우

- 변환할 수 없는 와이드 문자가 있는 경우

- 에 저장 된 바이트 수를 *mbstr* equals 버퍼 *개수*합니다.

대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).

경우 *개수* 특수 값인 [_TRUNCATE](../../c-runtime-library/truncate.md), 한 다음 **wcsrtombs_s** 만큼 문자열을 최대한 변환 null에 대 한 공간은 남겨 두고 대상 버퍼에 맞지 종결자입니다.

하는 경우 **wcsrtombs_s** 소스 문자열을 성공적으로 변환에서 null 종결자를 포함 하 여 변환된 된 문자열의 바이트 크기를 넣습니다  *&#42;pReturnValue* (제공  *pReturnValue* 아닙니다 **NULL**). 이런 경우에 합니다 *mbstr* 인수가 **NULL** 필요한 버퍼 크기를 결정 하는 방법을 제공 합니다. 경우 *mbstr* 됩니다 **NULL**에 *개수* 무시 됩니다.

하는 경우 **wcsrtombs_s** 멀티 바이트 문자를 변환할 수 없는 와이드 문자가-1을 넣습니다  *\*pReturnValue*, 대상 버퍼를 빈 문자열로 설정, 설정 **errno** 하 **EILSEQ**를 반환 합니다 **EILSEQ**합니다.

가리키는 시퀀스 하는 경우 *wcstr* 하 고 *mbstr* 겹치는 동작 **wcsrtombs_s** 정의 되지 않습니다. **wcsrtombs_s** 현재 로캘의 LC_TYPE 범주 영향입니다.

> [!IMPORTANT]
> 되도록 *wcstr* 및 *mbstr* 겹치지 않는 올바르고 *개수* 올바르게 변환할 와이드 문자 수를 반영 합니다.

합니다 **wcsrtombs_s** 함수에서 다른 [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) 해당 다시 시작할 수 있다는입니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어, 응용 프로그램 사용 **wcsrlen** 대신 **wcslen**경우에 대 한 후속 호출 **wcsrtombs_s** 대신 사용한 **wcstombs_s**.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

**wcsrtombs_s** 현재 스레드의 함수가 호출 함수는 다중 스레드 안전 **setlocale** 이 함수가 실행 중인 동안 하며 *mbstate* null입니다.

## <a name="example"></a>예제

```cpp
// crt_wcsrtombs_s.cpp
//
// This code example converts a wide
// character string into a multibyte
// character string.
//

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

void main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    errno_t         err;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);
    if (err == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfully converted.\n" );
    }
}
```

```Output
The string was successfully converted.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
