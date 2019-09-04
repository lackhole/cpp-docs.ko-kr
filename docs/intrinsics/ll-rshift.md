---
title: __ll_rshift
ms.date: 09/02/2019
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: ad17991d84acb7e531baf9435610ebd566197a22
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217492"
---
# <a name="__ll_rshift"></a>__ll_rshift

**Microsoft 전용**

첫 번째 매개 변수로 지정 된 64 비트 값을 두 번째 매개 변수로 지정 된 비트 수 만큼 오른쪽으로 이동 합니다.

## <a name="syntax"></a>구문

```C
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>매개 변수

*마스크할*\
진행 오른쪽으로 이동할 64 비트 정수 값입니다.

*nBit*\
진행 X 64에서 이동할 비트 수, x 64의 모듈로 64, x 86의 경우 모듈로 32

## <a name="return-value"></a>반환 값

비트로 이동 하 `nBit` 는 마스크입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

두 번째 매개 변수가 x64 (x 86의 경우 32)에서 64 보다 큰 경우 해당 숫자는 모듈로 64 (x 64의 32)를 사용 하 여 이동할 비트 수를 결정 합니다. 접두사 `ll` 는의 다른 이름인 64 비트 부호 있는 `long long`정수 형식에 대 `__int64`한 작업 임을 나타냅니다.

## <a name="example"></a>예제

```cpp
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

```Output
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

> [!NOTE]
> 을 `_ull_rshift` 사용 하는 경우 오른쪽으로 이동 된 값의 MSB 0이 되므로 음수 값의 경우 원하는 결과를 얻을 수 없습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)
