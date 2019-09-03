---
title: __rdtscp
ms.date: 09/02/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: 4dcabd6ed0f7fb3f422927815cbdc91f2b4b9d43
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221314"
---
# <a name="__rdtscp"></a>__rdtscp

**Microsoft 전용**

는 `rdtscp` 메모리에 대 한 `TSC_AUX[31:0`명령을 생성 하 고,는 64 비트 타임 스탬프 카운터를 반환 합니다`TSC)` (결과).

## <a name="syntax"></a>구문

```C
unsigned __int64 __rdtscp(
   unsigned int * AUX
);
```

### <a name="parameters"></a>매개 변수

*AUX*\
제한이 컴퓨터별 레지스터 `TSC_AUX[31:0]`의 콘텐츠를 포함 하는 위치에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

64 비트 부호 없는 정수 틱 수입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

내장 함수는 `rdtscp` 명령을 생성 합니다. `__rdtscp` 이 명령에 대 한 하드웨어 지원을 확인 하려면를 `__cpuid` 사용 `InfoType=0x80000001` 하 여 내장 함수를 호출 `CPUInfo[3] (EDX)`하 고 비트 27를 확인 합니다. 명령이 지원 되는 경우이 비트는 1이 고, 그렇지 않으면 0입니다.  `rdtscp` 명령을 지원 하지 않는 하드웨어에서 내장 함수를 사용 하는 코드를 실행 하는 경우 결과를 예측할 수 없습니다.

이 명령은 모든 이전 명령이 실행 되 고 모든 이전 로드가 전역적으로 표시 될 때까지 대기 합니다. 그러나 직렬화 명령이 아닙니다. 자세한 내용은 Intel 및 AMD 설명서를 참조 하십시오.

에서 `TSC_AUX[31:0]` 값의 의미는 운영 체제에 따라 달라 집니다.

## <a name="example"></a>예제

```cpp
#include <intrin.h>
#include <stdio.h>
int main()
{
    unsigned __int64 i;
    unsigned int ui;
    i = __rdtscp(&ui);
    printf_s("%I64d ticks\n", i);
    printf_s("TSC_AUX was %x\n", ui);
}
```

```Output
3363423610155519 ticks
TSC_AUX was 0
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__rdtsc](../intrinsics/rdtsc.md)\
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
