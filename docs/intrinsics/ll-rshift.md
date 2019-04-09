---
title: __ll_rshift
ms.date: 11/04/2016
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: e39f8fe797467569077dd24baf49670607915107
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041022"
---
# <a name="llrshift"></a>__ll_rshift

**Microsoft 전용**

오른쪽에 첫 번째 매개 변수로 지정 된 64 비트 값을 두 번째 매개 변수로 지정 된 비트 수 만큼 이동 합니다.

## <a name="syntax"></a>구문

```
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

#### <a name="parameters"></a>매개 변수

*마스크*<br/>
[in] 오른쪽 시프트 64 비트 정수 값입니다.

*nBit*<br/>
[in] X86 32 모듈로 및 x64에서 64 모듈로 이동할 비트 수입니다.

## <a name="return-value"></a>반환 값

으로 이동 하 여 마스크 `nBit` 비트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

두 번째 매개 변수 번호도 이동할 비트 수를 확인 하려면 64 (x86 32) 모듈로 수행 되는 (32) x86에서 x64 64 보다 큰 경우. `ll` 접두사에는 작업 임을 나타냅니다 `long long`다른 이름 `__int64`, 64 비트 부호 있는 정수 계열 형식입니다.

## <a name="example"></a>예제

```
// ll_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_rshift)

int main()
{
   __int64 Mask = - 0x100;
   int nBit = 4;
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
   Mask = __ll_rshift(Mask, nBit);
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
}
```

## <a name="output"></a>출력

```
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

**참고** 경우 `_ull_rshift` 되었습니다 사용 오른쪽 이동 값의 MSB 되었을 0 되므로 원하는 결과 하지 얻은 경우 음수 값입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)