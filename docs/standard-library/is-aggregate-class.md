---
title: is_aggregate 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_aggregate
helpviewer_keywords:
- is_aggregate
ms.openlocfilehash: 7d979d4e4019ada12b72fb563c0b969fffe2c12d
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268985"
---
# <a name="isaggregate-class"></a>is_aggregate 클래스

형식이 `aggregate`로 표시된 클래스 형식인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_aggregate;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 클래스 형식이 표시 되어 `aggregate`, 그렇지 않으면 false입니다. 하는 경우 *T* 클래스 형식에는 완전 한 형식 이어야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
