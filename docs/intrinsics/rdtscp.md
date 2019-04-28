---
title: __rdtscp
ms.date: 11/04/2016
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: b28052fbe0a1ab0e1a6f037ce61f43abea5cf771
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263063"
---
# <a name="rdtscp"></a>__rdtscp

**Microsoft 전용**

생성 합니다 `rdtscp` 명령 기록 `TSC_AUX[31:0`] 메모리를 64 비트 타임 스탬프 카운터 반환 (`TSC)` 결과입니다.

## <a name="syntax"></a>구문

```
unsigned __int64 __rdtscp(
   unsigned int * Aux
);
```

#### <a name="parameters"></a>매개 변수

*Aux*<br/>
[out] 컴퓨터의 특정 레지스터의 내용을 포함 하는 위치에 대 한 포인터 `TSC_AUX[31:0]`합니다.

## <a name="return-value"></a>반환 값

64 비트 부호 없는 정수 틱 수입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__rdtscp`|AMD NPT 제품군 0Fh 또는 이상 버전|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 내장 함수 생성을 `rdtscp` 명령입니다. 확인 하려면이 명령에 대 한 하드웨어 지원을 호출 합니다 `__cpuid` 포함 된 내장 함수 `InfoType=0x80000001` 27 많은 확인 및 `CPUInfo[3] (EDX)`합니다. 이 비트는 그렇지 않은 경우 명령 지원 되 면 1과 0입니다.  경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어를 `rdtscp` 명령 결과 예측할 수 없습니다.

> [!CAUTION]
>  와 달리 `rdtsc`, `rdtscp` 직렬화 명령; 컴파일러에서이 문제를 해결 하는 코드를 이동할 수는 그럼에도 불구 하 고 내장 함수입니다.

이전 버전의 x64 해석을 TSC 값의이 차세대 하드웨어는 다릅니다.  자세한 내용은 하드웨어 설명서를 참조 하세요.

값의 의미를 `TSC_AUX[31:0]` 운영 체제에 따라 달라 집니다.

## <a name="example"></a>예제

```
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

고급 마이크로 장치, inc 저작권 2007 All rights reserved. 고급 마이크로 장치, Inc. 사용 권한을 사용 하 여 재현

## <a name="see-also"></a>참고자료

[__rdtsc](../intrinsics/rdtsc.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)