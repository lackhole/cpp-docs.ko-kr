---
title: _mm_insert_si64, _mm_inserti_si64
ms.date: 11/04/2016
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
ms.openlocfilehash: f8c8f2f9b33588513e25b2290772aac464f46808
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033020"
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64, _mm_inserti_si64

**Microsoft 전용**

생성 된 `insertq` 명령 두 번째 피연산자의 첫 번째 피연산자에 비트를 삽입 합니다.

## <a name="syntax"></a>구문

```
__m128i _mm_insert_si64(
   __m128i Source1,
   __m128i Source2
);
__m128i _mm_inserti_si64(
   __m128i Source1,
   __m128i Source2
   int Length,
   int Index
);
```

#### <a name="parameters"></a>매개 변수

*Source1*<br/>
[in] 필드를 삽입 하는 하위 64 비트에서 입력된 데이터를 사용 하 여 128 비트 필드입니다.

*Source2*<br/>
[in] 해당 하위 비트에 삽입 하는 데이터로 128 비트 필드입니다.  에 대 한 `_mm_insert_si64`, 해당 상위 비트에서 필드 설명자를 포함 합니다.

*길이*<br/>
[in] 삽입할 필드의 길이 지정 하는 정수 상수입니다.

*인덱스*<br/>
[in] 데이터를 삽입 하는 필드의 최하위 비트 인덱스를 지정 하는 정수 상수입니다.

## <a name="return-value"></a>반환 값

해당 하위 64 비트의 원래 하위 64 비트를 포함 하는 128 비트 필드가 `Source1` 교체의 낮은 비트를 지정 된 비트 필드를 사용 하 여 `Source2`입니다. 반환 값의 상위 64 비트 정의 되지 않습니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_mm_insert_si64`|SSE4a|
|`_mm_inserti_si64`|SSE4a|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 내장 함수를 생성 합니다 `insertq` 명령에서 비트를 삽입할 `Source2` 에 `Source1`합니다. 두 가지 버전의 내장: `_mm_inserti_si64`를 즉시 버전이 및 `_mm_insert_si64` 즉시 아닌 것입니다.  각 버전 소스 2에서 지정 된 길이의 비트 필드를 추출 하 고 Source1에 삽입 합니다.  추출 된 비트가 Source2의 최하위 비트를 보여 줍니다.  이러한 비트를 삽입할 필드 Source1 길이 해당 비트의 인덱스에서 정의 됩니다.  길이 인덱스의 값은 64 mod, 모두-1에서 127 63으로 해석 됩니다 따라서 합니다. (감소) 비트 인덱스와 (감소) 필드 길이 합한 64 보다 큰 경우 결과가 정의 되지 않습니다. 필드 길이 0 값은 64로 해석 됩니다.  필드 길이 및 비트 인덱스를 둘 다 0 비트 63:0의 경우 `Source2` 삽입할 `Source1`합니다.  필드 길이가 0 인 비트 인덱스는 0이 아닌 경우 결과가 정의 되지 않습니다.

_Mm_insert_si64 호출, 필드 길이 소스 2와 bits 69:64에서 인덱스의 비트 77:72에 포함 됩니다.

호출 하는 경우 `_mm_inserti_si64` 정수 상수를 컴파일러가 확인할 수 없습니다는 인수를 사용 하 여 컴파일러는 XMM 레지스터에 해당 값을 압축 하 고 호출 하는 코드를 생성 `_mm_insert_si64`합니다.

에 대 한 하드웨어 지원을 확인 하는 `insertq` 명령 호출을 `__cpuid` 포함 된 내장 함수 `InfoType=0x80000001` 의 6 비트를 확인 하 고 `CPUInfo[2] (ECX)`입니다. 그렇지 않으면이 비트는 명령 지원 되 면 1과 0 수 있습니다. 경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어를 `insertq` 명령 결과 예측할 수 없습니다.

## <a name="example"></a>예제

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source1, source2, source3, result1, result2, result3;

int
main()
{

    __int64 mask;

    source1.ui64[0] = 0xffffffffffffffffll;
    source2.ui64[0] = 0xfedcba9876543210ll;
    source2.ui64[1] = 0xc10;
    source3.ui64[0] = source2.ui64[0];

    result1.m = _mm_insert_si64 (source1.m, source2.m);
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);
    mask = 0xffff << 12;
    mask = ~mask;
    result3.ui64[0] = (source1.ui64[0] & mask) |
                      ((source2.ui64[0] & 0xffff) << 12);

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;

}
```

```Output
result1 = 0xfffffffff3210fff
result2 = 0xfffffffff3210fff
result3 = 0xfffffffff3210fff
```

**Microsoft 전용 종료**

고급 마이크로 장치, inc 저작권 2007 All rights reserved. 고급 마이크로 장치, Inc. 사용 권한을 사용 하 여 재현

## <a name="see-also"></a>참고자료

[_mm_extract_si64, _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)