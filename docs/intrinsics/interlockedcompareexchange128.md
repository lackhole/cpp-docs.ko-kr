---
title: _InterlockedCompareExchange128
ms.date: 11/04/2016
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
ms.openlocfilehash: 9330b1405ca247364cd04d3ab399f66e4f332273
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037872"
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128

**Microsoft 전용**

128 비트 연관된 비교 및 교환을 수행합니다.

## <a name="syntax"></a>구문

```
unsigned char _InterlockedCompareExchange128(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out에서] 두 64 비트 정수의 배열 대상에 대 한 포인터 128 비트 필드로 간주 합니다. 대상 데이터에 일반 보호 오류를 방지 하려면 정렬 16 바이트 여야 합니다.

*ExchangeHigh*<br/>
[in] 대상의 상위 부분을 사용 하 여 교환할 수 있는 64 비트 정수입니다.

*ExchangeLow*<br/>
[in] 대상의 하위 부분으로 교환할 수 있는 64 비트 정수입니다.

*ComparandResult*<br/>
[out에서] (128 비트 필드로 간주 됨) 하는 두 개의 64 비트 정수 배열에 대 한 포인터를 대상으로 비교 합니다.  출력 시이 대상의 원래 값으로 덮어씁니다 되어 있습니다.

## <a name="return-value"></a>반환 값

128 비트 피비교수와 대상의 원래 값이 일치 하는 경우 1입니다. `ExchangeHigh` 및 `ExchangeLow` 128 비트 대상을 덮어씁니다.

비교 피연산자는 대상의 원래 값과 같지 않으면 0입니다. 대상의 값이 변경 되지 않습니다 및 대상의 값과 비교 피연산자의 값을 덮어씁니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_InterlockedCompareExchange128`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 내장 함수 생성 합니다 `cmpxchg16b` 명령 (사용 하 여는 `lock` 접두사) 128 비트 잠긴된 비교 및 교환 하는 데 있습니다. AMD 64 비트 하드웨어의 초기 버전에는이 명령을 지원 하지 않습니다. 에 대 한 하드웨어 지원을 확인 하는 `cmpxchg16b` 명령을 호출 합니다 `__cpuid` 포함 된 내장 함수 `InfoType=0x00000001 (standard function 1)`합니다. 13 많은 `CPUInfo[2]` 명령 지원 되는 경우 (ECX)는 1입니다.

> [!NOTE]
>  변수의 `ComparandResult` 을 항상 덮어씁니다. 후 합니다 `lock` 의 초기 값을 즉시 복사 하는 명령에이 내장 `Destination` 에 `ComparandResult`입니다. 이러한 이유로 `ComparandResult` 고 `Destination` 예기치 않은 문제를 방지 하려면 별도 메모리 위치를 가리켜야 합니다.

사용할 수 있지만 `_InterlockedCompareExchange128` 하위 수준 스레드 동기화에 대 한 필요가 없습니다 작은 동기화 함수를 사용할 수 있는 경우 128 비트 개를 동기화 하려면 (다른 같은 `_InterlockedCompareExchange` 내장 함수) 대신 합니다. 사용 하 여 `_InterlockedCompareExchange128` 메모리에는 128 비트 값에 대 한 원자성 액세스 하려는 경우.

경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어를 `cmpxchg16b` 명령 결과 예측할 수 없습니다.

이 루틴은 내장 함수로 사용할 수 있습니다.

## <a name="example"></a>예제

이 예제에서는 `_InterlockedCompareExchange128` 해당 높음 및 낮음 단어의 합계를 사용 하 여 두 개의 64 비트 정수 배열로 높은 단어를 대체 하는 데 하위 워드를 하나씩 늘립니다. BigInt.Int 배열에 대 한 액세스는 원자성 하지만이 예제에서는 단일 스레드를 사용 하 고 간단히 하기 위해 잠금을 무시 합니다.

```
// cmpxchg16b.c
// processor: x64
// compile with: /EHsc /O2
#include <stdio.h>
#include <intrin.h>

typedef struct _LARGE_INTEGER_128 {
    __int64 Int[2];
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;

volatile LARGE_INTEGER_128 BigInt;

// This AtomicOp() function atomically performs:
//   BigInt.Int[1] += BigInt.Int[0]
//   BigInt.Int[0] += 1
void AtomicOp ()
{
    LARGE_INTEGER_128 Comparand;
    Comparand.Int[0] = BigInt.Int[0];
    Comparand.Int[1] = BigInt.Int[1];
    do {
        ; // nothing
    } while (_InterlockedCompareExchange128(BigInt.Int,
                                            Comparand.Int[0] + Comparand.Int[1],
                                            Comparand.Int[0] + 1,
                                            Comparand.Int) == 0);
}

// In a real application, several threads contend for the value
// of BigInt.
// Here we focus on the compare and exchange for simplicity.
int main(void)
{
   BigInt.Int[1] = 23;
   BigInt.Int[0] = 11;
   AtomicOp();
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",
      BigInt.Int[1],BigInt.Int[0]);
}
```

```Output
BigInt.Int[1] = 34, BigInt.Int[0] = 12
```

**Microsoft 전용 종료**

고급 마이크로 장치, inc 저작권 2007 All rights reserved. 고급 마이크로 장치, Inc. 사용 권한을 사용 하 여 재현

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[_InterlockedCompareExchange 내장 함수](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)<br/>
[x86 컴파일러와 충돌](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)