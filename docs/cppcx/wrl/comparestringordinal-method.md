---
title: CompareStringOrdinal 메서드
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: a1ac0576bdd374daa5cbd445af480e7652b61e45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398708"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal 메서드

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
비교할 첫 번째 HSTRING입니다.

*rhs*<br/>
비교할 두 번째 HSTRING입니다.

## <a name="return-value"></a>반환 값

|값|조건|
|-----------|---------------|
|-1|*lhs* 는 보다 작은 *rhs*합니다.|
|0|*lhs* equals *rhs*합니다.|
|1|*lhs* 보다 크면 *rhs*합니다.|

## <a name="remarks"></a>설명

두 지정 된 HSTRING 개체를 비교 하 고 정렬 순서에서 상대 위치를 나타내는 정수를 반환 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>참고자료

[Microsoft::WRL::Wrappers::Details 네임스페이스](microsoft-wrl-wrappers-details-namespace.md)