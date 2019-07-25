---
title: is_move_constructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: c83ed4365fd0e73a7daa8b9894c5e85f20387a79
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456111"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible 클래스

형식에 이동 생성자가 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>매개 변수

*트*\
평가할 형식입니다.

## <a name="remarks"></a>설명

이동 작업을 사용 하 여 *T* 형식을 생성할 수 있는 경우 true로 평가 되는 형식 조건자입니다. 이 조건자는 `is_constructible<T, T&&>`과 같습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
