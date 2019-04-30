---
title: rand_s
ms.date: 1/02/2018
apiname:
- rand_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rand_s
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: d196a6f5d7483deb9a7e1b8d7fa929532b6197db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358127"
---
# <a name="rands"></a>rand_s

의사 난수를 생성합니다. 함수의 더 안전한 버전을 이것이 [rand](rand.md)에 설명 된 대로 보안 기능이 향상 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.

## <a name="syntax"></a>구문

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>매개 변수

*randomValue*<br/>
생성 된 값을 저장 하는 정수에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0이고 그렇지 않으면 오류 코드입니다. 하는 경우 입력된 포인터 _했습니다_ 가 null 포인터인 경우 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 함수 반환 **EINVAL** 설정 **errno** 하 **EINVAL**합니다. 함수가 다른 이유로 실패 하면 *_했습니다_ 0으로 설정 됩니다.

## <a name="remarks"></a>설명

합니다 **rand_s** 함수는 범위는 0에 의사 난수 정수를 씁니다 **UINT_MAX** 입력된 포인터에 대 한 합니다. 합니다 **rand_s** 함수 운영 체제를 사용 하 여 암호화 보안 난수를 생성 합니다. 생성 한 시드를 사용 하지 않는 합니다 [srand](srand.md) 함수에서 사용 하는 난수 시퀀스 어떤 영향이 나 [rand](rand.md)합니다.

합니다 **rand_s** 함수에는 상수 **_CRT_RAND_S** 다음 예제와 같이 선언 하려는 함수의 포함 문 이전에 정의 합니다.

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** 에 따라 달라 집니다 합니다 [RtlGenRandom](/windows/desktop/api/ntsecapi/nf-ntsecapi-rtlgenrandom) API만 이상 Windows XP에서 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**rand_s**|\<stdlib.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_rand_s.c
// This program illustrates how to generate random
// integer or floating point numbers in a specified range.

// Remembering to define _CRT_RAND_S prior
// to inclusion statement.
#define _CRT_RAND_S

#include <stdlib.h>
#include <stdio.h>
#include <limits.h>

int main( void )
{
    int             i;
    unsigned int    number;
    double          max = 100.0;
    errno_t         err;

    // Display 10 random integers in the range [ 1,10 ].
    for( i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %u\n", (unsigned int) ((double)number /
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);
    }

    printf_s("\n");

    // Display 10 random doubles in [0, max).
    for (i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %g\n", (double) number /
                          ((double) UINT_MAX + 1) * max );
    }
}
```

### <a name="sample-output"></a>샘플 출력

```Output
10
4
5
2
8
2
5
6
1
1

32.6617
29.4471
11.5413
6.41924
20.711
60.2878
61.0094
20.1222
80.9192
65.0712
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
[srand](srand.md)<br/>
