---
title: _mm_stream_ss
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: 76c6c848351df773b9857b2f83726b64db982d9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263232"
---
# <a name="mmstreamss"></a>_mm_stream_ss

**Microsoft 전용**

캐시를 오염 시 키 지 않고 메모리 위치에 32 비트 데이터를 씁니다.

## <a name="syntax"></a>구문

```
void _mm_stream_ss(
   float * Dest,
   __m128 Source
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out] 원본 데이터가 기록 되는 위치에 대 한 포인터입니다.

*소스*<br/>
[in] 포함 하는 128 비트 숫자를 `float` 32 비트 아래쪽에 쓸 값...

## <a name="return-value"></a>반환 값

없음

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 내장 함수 생성을 `movntss` 명령입니다. 확인 하려면이 명령에 대 한 하드웨어 지원을 호출 합니다 `__cpuid` 포함 된 내장 함수 `InfoType=0x80000001` 의 6 비트를 확인 하 고 `CPUInfo[2] (ECX)`입니다. 이 비트는 그렇지 않은 경우 명령에 지원 되는 경우 1과 0입니다.

사용 하는 코드를 실행 하는 경우는 `_mm_stream_ss` 하드웨어를 지원 하지 않는 내장 함수는 `movntss` 명령 결과 예측할 수 없습니다.

## <a name="example"></a>예제

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128 vals;
    float f[4];

    f[0] = -1.;
    f[1] = -2.;
    f[2] = -3.;
    f[3] = -4.;
    vals.m128_f32[0] = 0.;
    vals.m128_f32[1] = 1.;
    vals.m128_f32[2] = 2.;
    vals.m128_f32[3] = 3.;
    _mm_stream_ss(&f[3], vals);
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;
}
```

```Output
f[0] = -1, f[1] = -2
f[2] = -3, f[3] = 3
```

**Microsoft 전용 종료**

고급 마이크로 장치, inc 저작권 2007 All rights reserved. 고급 마이크로 장치, Inc. 사용 권한을 사용 하 여 재현

## <a name="see-also"></a>참고자료

[_mm_stream_sd](../intrinsics/mm-stream-sd.md)<br/>
[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)<br/>
[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)