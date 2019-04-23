---
title: _mm_cvtss_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_cvtss_si64x
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
ms.openlocfilehash: a3b7ece325d975045046e865e6b090f3f6729558
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036828"
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x

**Microsoft 전용**

확장 x64 생성 된 변환 스칼라 단일 정밀도 부동 소수점 숫자의 64 비트 정수를 버전 (`cvtss2si`) 명령입니다.

## <a name="syntax"></a>구문

```
__int64 _mm_cvtss_si64x(
   __m128 value
);
```

#### <a name="parameters"></a>매개 변수

*값*<br/>
[in] `__m128` 부동 소수점 값을 포함 하는 구조체.

## <a name="return-value"></a>반환 값

64 비트 정수를 첫 번째 부동 소수점 값을 정수로 변환의 결과입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_mm_cvtss_si64x`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

구조 값의 첫 번째 요소를 정수로 변환 되 고 반환 합니다. MXCSR에서 반올림 제어 비트를 반올림 동작을 결정 하는 데 사용 됩니다. 기본 반올림 모드는 가까운 소수 부분은 0.5 경우 숫자를 반올림를 반올림 합니다. 때문에 `__m128` 구조 XMM 레지스터에서 XMM 레지스터는이 내장 함수는 값을 나타내는 한 시스템 메모리에 씁니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```
// _mm_cvtss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] =
                           { 101.25, 200.75, 300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvtss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__m128d](../cpp/m128d.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)