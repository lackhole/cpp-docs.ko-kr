---
title: _STATIC_ASSERT 매크로
ms.date: 11/04/2016
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
apitype: DLLExport
f1_keywords:
- _STATIC_ASSERT
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
ms.openlocfilehash: 5d3aa1d9665b48a0690d8eb62353fc98c5a550f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354700"
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT 매크로

컴파일 시 식을 계산 하 고 결과가 인 경우 오류를 생성 **FALSE**합니다.

## <a name="syntax"></a>구문

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>매개 변수

*booleanExpression*<br/>
0이 아닌 값으로 계산 되는 식 (포인터 포함) (**TRUE**) 또는 0 (**FALSE**).

## <a name="remarks"></a>설명

이 매크로 유사 합니다 [_ASSERT 및 _ASSERTE 매크로](assert-asserte-assert-expr-macros.md)점을 제외 하 고 *booleanExpression* 런타임 대신 컴파일 시간에 평가 됩니다. 하는 경우 *booleanExpression* 로 평가 **FALSE** (0), [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) 생성 됩니다.

## <a name="example"></a>예제

확인이 예제에서는 여부를 [sizeof](../../c-language/sizeof-operator-c.md) 는 **int** 2 바이트 보다 크거나 같은 경우는 여부에 관계 없이 [sizeof](../../c-language/sizeof-operator-c.md) 를 **긴** 1 바이트입니다. 프로그램을 컴파일되지 것입니다 및 생성 됩니다 [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) 때문에 **긴** 1 바이트 보다 큽니다.

```C
// crt__static_assert.c

#include <crtdbg.h>
#include <stdio.h>

_STATIC_ASSERT(sizeof(int) >= 2);
_STATIC_ASSERT(sizeof(long) == 1);  // C2466

int main()
{
    printf("I am sure that sizeof(int) will be >= 2: %d\n",
        sizeof(int));
    printf("I am not so sure that sizeof(long) == 1: %d\n",
        sizeof(long));
}
```

## <a name="requirements"></a>요구 사항

|매크로|필수 헤더|
|-----------|---------------------|
|**_STATIC_ASSERT**|\<crtdbg.h>|

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](assert-asserte-assert-expr-macros.md)<br/>
