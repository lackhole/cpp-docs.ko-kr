---
title: __ull_rshift
ms.date: 11/04/2016
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: 5d62ec1526aff595c14a53e9eca43a7a3118c8fa
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034526"
---
# <a name="ullrshift"></a>__ull_rshift

**Microsoft 전용**

x64에서 오른쪽으로 첫 번째 매개 변수로 지정 된 64 비트 값을 두 번째 매개 변수로 지정 된 비트 수 만큼 이동 합니다.

## <a name="syntax"></a>구문

```
unsigned __int64 __ull_rshift(
   unsigned __int64 mask, 
   int nBit
);
```

#### <a name="parameters"></a>매개 변수

*마스크*<br/>
[in] 오른쪽 시프트 64 비트 정수 값입니다.

*nBit*<br/>
[in] X86, 32 모듈로 및 x64 64 모듈로 이동할 비트 수입니다.

## <a name="return-value"></a>반환 값

으로 이동 하 여 마스크 `nBit` 비트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

두 번째 매개 변수 31 이동할 비트 수를 결정할 수 32 (x64 64) 모듈로 수행 되는 x86 (x64 63) 보다 큰 경우. 합니다 `ull` 이름을 나타냅니다 `unsigned long long (unsigned __int64)`합니다.

## <a name="example"></a>예제

```
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

## <a name="output"></a>출력

```
1
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ll_rshift](../intrinsics/ll-rshift.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)