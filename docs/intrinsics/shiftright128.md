---
title: __shiftright128
ms.date: 11/04/2016
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: b721abc9be22709fdc221951e2012300d6b96762
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030104"
---
# <a name="shiftright128"></a>__shiftright128

**Microsoft 전용**

두 개의 64비트 수량 `LowPart` 및 `HighPart`로 표현되는 128비트 수량을 `Shift`로 지정된 비트 수만큼 오른쪽으로 이동하고 결과 중 하위 64비트를 반환합니다.

## <a name="syntax"></a>구문

```
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

#### <a name="parameters"></a>매개 변수

*LowPart*<br/>
[in] 이동할 128 비트 수량 중 하위 64 비트입니다.

*HighPart*<br/>
[in] 이동할 128 비트 수량 중 상위 64 비트입니다.

*Shift*<br/>
[in] 이동할 비트 수입니다.

## <a name="return-value"></a>반환 값

결과의 하위 64비트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__shiftright128`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`Shift` 값은 항상 64로 나눈 나머지이므로 예를 들어 `__shiftright128(0, 1, 64)`를 호출하면 함수는 상위 부분의 `0`비트를 오른쪽으로 이동하고 일반적인 경우에 반환되는 `0`이 아닌 하위 부분 `1`을 반환합니다.

## <a name="example"></a>예제

예를 들어 참조 [__shiftleft128](../intrinsics/shiftleft128.md)합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__shiftleft128](../intrinsics/shiftleft128.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)