---
title: _mm_stream_sd
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_sd
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
ms.openlocfilehash: 3555b71e15d6f9c618a83f573d6da3cda9e7b705
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263245"
---
# <a name="mmstreamsd"></a>_mm_stream_sd

**Microsoft 전용**

캐시를 오염 시 키 지 않고 메모리 위치를 64 비트 데이터를 씁니다.

## <a name="syntax"></a>구문

```
void _mm_stream_sd(
   double * Dest,
   __m128d Source
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out] 원본 데이터를 쓸 위치를 위치에 대 한 포인터입니다.

*소스*<br/>
[in] 포함 하는 128 비트 값의 `double` 64 비트 아래쪽에 쓸 값...

## <a name="return-value"></a>반환 값

없음

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_mm_stream_sd`|SSE4a|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 내장 함수 생성을 `movntsd` 명령입니다. 확인 하려면이 명령에 대 한 하드웨어 지원을 호출 합니다 `__cpuid` 포함 된 내장 함수 `InfoType=0x80000001` 의 6 비트를 확인 하 고 `CPUInfo[2] (ECX)`입니다. 하드웨어에서 지 원하는 경우이 지침 및 0 그렇지 않으면이 비트는 1입니다.

사용 하는 코드를 실행 하는 경우는 `_mm_stream_sd` 하드웨어를 지원 하지 않는 내장 함수는 `movntsd` 명령 결과 예측할 수 없습니다.

## <a name="example"></a>예제

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128d vals;
    double d[2];

    d[0] = -1.;
    d[1] = -2.;
    vals.m128d_f64[0] = 0.;
    vals.m128d_f64[1] = 1.;
    _mm_stream_sd(&d[1], vals);
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;
}
```

```Output
d[0] = -1, d[1] = 1
```

**Microsoft 전용 종료**

고급 마이크로 장치, inc 저작권 2007 All rights reserved. 고급 마이크로 장치, Inc. 사용 권한을 사용 하 여 재현

## <a name="see-also"></a>참고자료

[_mm_stream_ss](../intrinsics/mm-stream-ss.md)<br/>
[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)