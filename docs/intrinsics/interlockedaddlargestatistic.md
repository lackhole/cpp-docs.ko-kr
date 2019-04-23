---
title: _InterlockedAddLargeStatistic
ms.date: 11/04/2016
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: 6f9d599a8d7668c6c8a37846275e8338002589d1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033416"
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Microsoft 전용**

첫 번째 피연산자가 64 비트 값 인 연관된 추가 수행 합니다.

## <a name="syntax"></a>구문

```
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

#### <a name="parameters"></a>매개 변수

*가 수*<br/>
[out에서] 추가 작업의 첫 번째 피연산자에 대 한 포인터입니다. 가리킨 값을 더하기의 결과 의해 대체 됩니다.

*값*<br/>
[in] 두 번째 피연산자입니다. 첫 번째 피연산자에 추가할 값입니다.

## <a name="return-value"></a>반환 값

두 번째 피연산자의 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

별도 두 잠긴된 지침으로 구현 되므로 내장 함수는 원자성 없습니다. 다른 스레드에서 실행 중에 발생이 내장 함수는 원자성 64-bit 읽기를 읽고 일관 되지 않은 값을 될 수 있습니다.

이 함수는 읽기 / 쓰기 장벽으로 작동합니다. 자세한 내용은 [_ReadWriteBarrier](../intrinsics/readwritebarrier.md)합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[x86 컴파일러와 충돌](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)