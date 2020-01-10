---
title: alignment_of 클래스
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: d241848edf57fe4876c35e22f1762abf5d6888fa
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302317"
---
# <a name="alignment_of-class"></a>alignment_of 클래스

지정된 형식의 맞춤을 가져옵니다. 이 구조체는 [alignof](../cpp/alignment-cpp-declarations.md) 측면에서 구현됩니다. 맞춤 값을 쿼리해야 하는 경우에는 **alignof** 을 직접 사용 해야 합니다. 태그 디스패치를 수행하는 경우처럼 정수 계열 상수가 필요한 경우 alignment_of를 사용합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>매개 변수

*Ty*\
형식이 쿼리입니다.

## <a name="remarks"></a>주의

형식 쿼리는 *Ty*형식의 맞춤 값을 보유 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits >

**네임스페이스:** std

## <a name="see-also"></a>참조

[<type_traits>](../standard-library/type-traits.md)\
[aligned_storage 클래스](../standard-library/aligned-storage-class.md)
