---
title: Container Class::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: b344747c42e9b8b751b97747aacec0b39d10d6a1
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221521"
---
# <a name="container-classswap"></a>Container Class::swap

> [!NOTE]
> 이 항목은 Microsoft C++ 설명서에 사용 되는 컨테이너의 작동 하지 않는 예로 C++ 표준 라이브러리입니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

**\*this**와 해당 인수 간에 제어되는 시퀀스를 교환합니다.

## <a name="syntax"></a>구문

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>설명

**\*this.get\_allocator ==** _right_ **.get_allocator**인 경우 일정한 시간 내에 교환합니다. 그렇지 않으면 두 개의 제어되는 시퀀스에 있는 요소 수에 비례하여 많은 요소 할당 및 생성자 호출을 수행합니다.

## <a name="see-also"></a>참고자료

[샘플 컨테이너 클래스](../standard-library/sample-container-class.md)<br/>
