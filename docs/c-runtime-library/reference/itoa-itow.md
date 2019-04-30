---
title: _itoa, _itow 함수
ms.date: 03/21/2018
apiname:
- itoa
- _itoa
- ltoa
- _ltoa
- ultoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
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
- _itoa
- _ltoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- itoa
- ltoa
- ultoa
- i64toa
- ui64toa
- itow
- ltow
- ultow
- i64tow
- ui64tow
- itot
- _itot
- ltot
- _ltot
- ultot
- _ultot
- i64tot
- _i64tot
- ui64tot
- _ui64tot
- _MAX_ITOSTR_BASE16_COUNT
- _MAX_ITOSTR_BASE10_COUNT
- _MAX_ITOSTR_BASE8_COUNT
- _MAX_ITOSTR_BASE2_COUNT
- _MAX_LTOSTR_BASE16_COUNT
- _MAX_LTOSTR_BASE10_COUNT
- _MAX_LTOSTR_BASE8_COUNT
- _MAX_LTOSTR_BASE2_COUNT
- _MAX_ULTOSTR_BASE16_COUNT
- _MAX_ULTOSTR_BASE10_COUNT
- _MAX_ULTOSTR_BASE8_COUNT
- _MAX_ULTOSTR_BASE2_COUNT
- _MAX_I64TOSTR_BASE16_COUNT
- _MAX_I64TOSTR_BASE10_COUNT
- _MAX_I64TOSTR_BASE8_COUNT
- _MAX_I64TOSTR_BASE2_COUNT
- _MAX_U64TOSTR_BASE16_COUNT
- _MAX_U64TOSTR_BASE10_COUNT
- _MAX_U64TOSTR_BASE8_COUNT
- _MAX_U64TOSTR_BASE2_COUNT
helpviewer_keywords:
- _itot function
- ui64toa function
- _ui64toa function
- converting integers
- itot function
- _i64tow function
- _i64toa function
- _itow function
- ui64tow function
- integers, converting
- itoa function
- _ui64tow function
- i64tow function
- itow function
- i64toa function
- converting numbers, to strings
- _itoa function
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
ms.openlocfilehash: 016f3474345b623415be9fe33556bb9f466542ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157372"
---
# <a name="itoa-itoa-ltoa-ltoa-ultoa-ultoa-i64toa-ui64toa-itow-ltow-ultow-i64tow-ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

정수를 문자열로 변환합니다. 이러한 함수의 더 안전한 버전은 사용할 수 있습니다. 참조 [_itoa_s, _itow_s 함수](itoa-s-itow-s.md)합니다.

## <a name="syntax"></a>구문

```C
char * _itoa( int value, char *buffer, int radix );
char * _ltoa( long value, char *buffer, int radix );
char * _ultoa( unsigned long value, char *buffer, int radix );
char * _i64toa( long long value, char *buffer, int radix );
char * _ui64toa( unsigned long long value, char *buffer, int radix );

wchar_t * _itow( int value, wchar_t *buffer, int radix );
wchar_t * _ltow( long value, wchar_t *buffer, int radix );
wchar_t * _ultow( unsigned long value, wchar_t *buffer, int radix );
wchar_t * _i64tow( long long value, wchar_t *buffer, int radix );
wchar_t * _ui64tow( unsigned long long value, wchar_t *buffer, int radix );

// These Posix versions of the functions have deprecated names:
char * itoa( int value, char *buffer, int radix );
char * ltoa( long value, char *buffer, int radix );
char * ultoa( unsigned long value, char *buffer, int radix );

// The following template functions are C++ only:
template <size_t size>
char *_itoa( int value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( long value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
char *_i64toa( long long value, char (&buffer)[size], int radix );

template <size_t size>
char * _ui64toa( unsigned long long value, char (&buffer)[size], int radix );

template <size_t size>
wchar_t * _itow( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ltow( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ultow( unsigned long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _i64tow( long long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ui64tow( unsigned long long value, wchar_t (&buffer)[size],
   int radix );
```

### <a name="parameters"></a>매개 변수

*값*<br/>
변환할 숫자입니다.

*buffer*<br/>
변환의 결과 포함 하는 버퍼입니다.

*radix*<br/>
변환에 사용할 기본 *값*, 2 개에서 36 개의 범위의 이어야 합니다.

*size*<br/>
문자 유형의 단위 버퍼의 길이입니다. 이 매개 변수에서 유추 되는 *버퍼* 인수에서 C++합니다.

## <a name="return-value"></a>반환 값

이러한 각 함수에 대 한 포인터를 반환 *버퍼*합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

합니다 **_itoa**를 **_ltoa**를 **_ultoa**를 **_i64toa**, 및 **_ui64toa** 의 자리를 변환 하는 함수 지정 된 *값* 인수를 null로 끝나는 문자열을 결과 저장소 (최대 33 자 **_itoa**를 **_ltoa**, 및  **_ultoa**, 및에 대 한 65 **_i64toa** 하 고 **_ui64toa**)에서 *버퍼*합니다. 하는 경우 *기 수* 10 같음 및 *값* 가 음수인 경우 저장된 된 문자열의 첫 번째 문자는 음수 기호 (**-**). 합니다 **_itow**를 **_ltow**를 **_ultow**를 **_i64tow**, 및 **_ui64tow** 함수는 와이드 문자 버전의 **_itoa**, **_ltoa**합니다 **_ultoa**를 **_i64toa**, 및 **_ui64toa**, 각각.

> [!IMPORTANT]
> 이러한 함수는 너무 작으면 버퍼의 끝을 지난 작성할 수 있습니다. 버퍼 오버런을 방지 하려면 *버퍼* 작아서 변환 된 숫자와 후행 null 문자 및 기호 문자를 포함 합니다. 이러한 함수를 잘못 사용 하면 코드의 심각한 보안 문제가 발생할 수 있습니다.

기본적으로 보안 문제에 대 한 잠재력 인해 이러한 함수는 사용 중단 경고를 발생 [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **이 함수 또는 변수 안전 하지 않을 수 있습니다. 사용 하는 것이 좋습니다** *safe_function* **대신 합니다. 사용 중단을 사용 하지 않으려면 _CRT_SECURE_NO_WARNINGS를 사용 합니다.** 사용 하도록 소스 코드를 변경 하는 것이 좋습니다 합니다 *safe_function* 경고 메시지에서 제안 합니다. 더 안전한 함수는 지정 된 버퍼 크기 보다 많은 문자를 작성 하지 마십시오. 자세한 내용은 [_itoa_s, _itow_s 함수](itoa-s-itow-s.md)합니다.

사용 중단 경고가 없는 이러한 함수를 사용 하려면 정의 된 **_CRT_SECURE_NO_WARNINGS** CRT 헤더를 포함 하기 전에 전처리기 매크로입니다. 추가 하 여 개발자 명령 프롬프트에서 명령줄에서 이렇게 하려면 합니다 **/D_CRT_SECURE_NO_WARNINGS** 컴파일러 옵션을 합니다 **cl** 명령입니다. 그렇지 않으면 소스 파일에서 매크로 정의 합니다. 미리 컴파일된 헤더를 사용 하면 미리 컴파일된 헤더의 맨 위에 있는 매크로 정의할 파일을 일반적으로 stdafx.h를 포함 합니다. 소스 코드에서 매크로 정의 사용 된 **#define** 지시문이이 예제와 같이 모든 CRT 헤더를 포함 하기 전에:

```C
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++에서 이러한 함수는 안전 하 게 대응을 호출 하는 템플릿 오버 로드 합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

Posix 이름을 **itoa**를 **ltoa**, 및 **ultoa** 에 대 한 별칭으로 존재 합니다 **_itoa**를 **_ltoa**, 및 **_ultoa** 함수입니다. Posix 이름은 ISO C의 구현 별 함수 이름 규칙을 따르지 때문에 사용 되지 않음 기본적으로 이러한 함수는 사용 중단 경고를 발생 [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **이 항목에 대 한 POSIX 이름은 사용 되지 않습니다. 대신 ISO C를 사용 하 고 C++ 와 호환 되는 이름:** *new_name*합니다. 이러한 함수의 더 안전한 버전을 사용 하도록 소스 코드를 변경 하는 것이 좋습니다 **_itoa_s**하십시오 **_ltoa_s**, 또는 **_ultoa_s**합니다. 자세한 내용은 [_itoa_s, _itow_s 함수](itoa-s-itow-s.md)합니다.

소스 코드 이식성에 대 한 코드에서 Posix 이름을 유지 하는 것이 좋습니다. 사용 중단 경고가 없는 이러한 함수를 사용 하려면 둘 다를 정의 합니다 **_CRT_NONSTDC_NO_WARNINGS** 하 고 **_CRT_SECURE_NO_WARNINGS** CRT 헤더를 포함 하기 전에 전처리기 매크로입니다. 추가 하 여 개발자 명령 프롬프트에서 명령줄에서 이렇게 하려면 합니다 **/D_CRT_SECURE_NO_WARNINGS** 하 고 **/D_CRT_NONSTDC_NO_WARNINGS** 컴파일러 옵션을 **cl**명령입니다. 그렇지 않으면 소스 파일에서 매크로 정의 합니다. 미리 컴파일된 헤더를 사용 하면 정의 미리 컴파일된 헤더의 맨 위에 있는 매크로 일반적으로 stdafx.h 파일을 포함 합니다. 소스 코드에서 매크로 정의 하려면 사용할 **#define** 지시문이이 예제와 같이 모든 CRT 헤더를 포함 하기 전에:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>최대 변환 수 매크로

CRT를 변환에 대 한 보안 버퍼를 만들 수 있도록 몇 가지 편리한 매크로 포함 합니다. 이러한 각 정수 형식에 null 종결자를 포함 하 여 가능한 가장 긴 값을 변환 하는 데 필요한 버퍼의 크기를 정의 하 고 몇 가지 일반적인 자료에 대 한 문자를 로그인 합니다. 변환 버퍼 변환 하 여 지정 된 밑에서 수신 하기에 충분 한지 확인 합니다 *기 수*, 버퍼를 할당 하는 경우 다음 중 하나 사용 하 여 매크로 정의 합니다. 정수 계열 형식 문자열로 변환 하는 경우 버퍼 오버런 오류를 방지 하기 위해 이렇게 합니다. Stdlib.h 또는 wchar.h 원본에 포함 하면 이러한 매크로 정의 됩니다.

이러한 매크로 중 하나에서 문자열 변환 함수를 사용 하려면 적절 한 문자 형식의 변환 버퍼를 선언 하 고 버퍼 차원으로 정수 형식 및 기본에 대 한 매크로 값을 사용 합니다. 이 표에 나열 된 자료에 대 한 각 함수에 대 한 적절 한 매크로 나와 있습니다.

||||
|-|-|-|
|함수|radix|매크로|
|**_itoa**, **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

변환 개수 매크로 사용 하 여 버퍼를 포함할 수 있는 크기를 정의 하는이 예제는 **부호 없는 long long** 기본 2에서:

```cpp
#include <wchar.h>
#include <iostream>
int main()
{
    wchar_t buffer[_MAX_U64TOSTR_BASE2_COUNT];
    std:wcout << _ui64tow(0xFFFFFFFFFFFFFFFFull, buffer, 2) << std::endl;
}
```

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot**|**_itoa**|**_itoa**|**_itow**|
|**_ltot**|**_ltoa**|**_ltoa**|**_ltow**|
|**_ultot**|**_ultoa**|**_ultoa**|**_ultow**|
|**_i64tot**|**_i64toa**|**_i64toa**|**_i64tow**|
|**_ui64tot**|**_ui64toa**|**_ui64toa**|**_ui64tow**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**itoa**, **ltoa**, **ultoa**|\<stdlib.h>|
|**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, **_ui64toa**|\<stdlib.h>|
|**_itow**, **_ltow**, **_ultow**, **_i64tow**, **_ui64tow**|\<stdlib.h> 또는 \<wchar.h>|

이러한 함수 및 매크로 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 샘플의 일부 정수 변환 함수가 사용 하는 방법을 보여 줍니다. 사용 된 **_CRT_SECURE_NO_WARNINGS** 매크로를 C4996 경고를 억제 합니다.

```C
// crt_itoa.c
// Compile by using: cl /W4 crt_itoa.c
// This program makes use of the _itoa functions
// in various examples.

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen
#include <stdlib.h>     // for _countof, _itoa fns, _MAX_COUNT macros

int main(void)
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;

    for (r = 10; r >= 2; --r)
    {
        _itoa(-1, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _i64toa(-1LL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _ui64toa(0xffffffffffffffffULL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s, _itow_s functions](itoa-s-itow-s.md)<br/>
