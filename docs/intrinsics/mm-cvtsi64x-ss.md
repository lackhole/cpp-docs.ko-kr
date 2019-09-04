---
title: _mm_cvtsi64x_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtsi64x_ss
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
ms.openlocfilehash: 0e9bacc56f212e804467d1c6e0159a1749235976
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217462"
---
# <a name="_mm_cvtsi64x_ss"></a>_mm_cvtsi64x_ss

**Microsoft 전용**

64 비트 정수 변환의 x64 확장 버전을 스칼라 단 정밀도 부동 소수점 값 (`cvtsi2ss`) 명령으로 생성 합니다.

## <a name="syntax"></a>구문

```C
__m128 _mm_cvtsi64x_ss(
   __m128 a,
   __int64 b
);
```

### <a name="parameters"></a>매개 변수

*은*\
진행 네 `__m128` 개의 단 정밀도 부동 소수점 값을 포함 하는 구조체입니다.

*b*\
진행 부동 소수점 값으로 변환할 64 비트 정수입니다.

## <a name="return-value"></a>반환 값

변환 결과에 해당 하는 첫 번째 부동 소수점 값을 갖는 구조체입니다.`__m128` 다른 세 값은에서 변경 되지 않은상태로 복사 됩니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_mm_cvtsi64x_ss`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

구조체 `__m128` 는 xmm 레지스터를 나타내므로 내장 함수는 시스템 메모리의 *b* 값을 xmm 레지스터로 이동할 수 있도록 허용 합니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```cpp
// _mm_cvtsi64x_ss.cpp
// processor: x64

#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtsi64x_ss)

int main()
{
    __m128 a;
    __int64 b = 54;

    a.m128_f32[0] = 0;
    a.m128_f32[1] = 0;
    a.m128_f32[2] = 0;
    a.m128_f32[3] = 0;
    a = _mm_cvtsi64x_ss(a, b);

    printf_s( "%lf %lf %lf %lf\n",
              a.m128_f32[0], a.m128_f32[1],
              a.m128_f32[2], a.m128_f32[3] );
}
```

```Output
54.000000 0.000000 0.000000 0.000000
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__m128](../cpp/m128.md)\
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
