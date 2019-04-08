---
title: _mm_cvttss_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: cfdea6ded622cbcbe42bd555edb3029fabad7823
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023713"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x

**Microsoft 전용**

내보내는 확장 x64 버전의 64 비트 정수로 잘림 단 정밀도 부동 소수점 숫자를 사용 하 여 변환 (`cvttss2si`) 명령입니다.

## <a name="syntax"></a>구문

```
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

#### <a name="parameters"></a>매개 변수

*값*<br/>
[in] `__m128` 단 정밀도 부동 소수점 값이 포함 된 구조입니다.

## <a name="return-value"></a>반환 값

첫 번째 부동 소수점 값을 64 비트 정수로 변환의 결과입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_mm_cvttss_si64x`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

내장 함수에서 다른 `_mm_cvtss_si64x` 만 부정확 한 변환을 0으로 잘립니다. 때문에 `__m128` 구조는 XMM 레지스터를 나타내며, 생성 지침을 XMM 레지스터에서 시스템 메모리에 데이터를 이동 합니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__m128](../cpp/m128.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)