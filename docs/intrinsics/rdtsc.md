---
title: __rdtsc
ms.date: 11/04/2016
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 6f30be3340ae1be237bb2f8a008a8cb60c7351f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396576"
---
# <a name="rdtsc"></a>__rdtsc

**Microsoft 전용**

생성 된 `rdtsc` 프로세서 타임 스탬프를 반환 하는 명령입니다. 프로세서 시간 스탬프를 마지막 다시 설정 이후 클록 주기 수를 기록합니다.

## <a name="syntax"></a>구문

```
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>반환 값

틱 수를 나타내는 64 비트 부호 없는 정수입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 루틴은 내장 함수로 사용할 수 있습니다.

이전 버전의 x64 해석을 TSC 값의이 차세대 하드웨어는 다릅니다. 자세한 내용은 하드웨어 설명서를 참조 하세요.

## <a name="example"></a>예제

```
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)