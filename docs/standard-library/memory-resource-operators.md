---
title: '&lt;memory_resource&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- memory_resource/std::operator!=
- memory_resource/std::operator==
helpviewer_keywords:
- std::operator!= (memory_resource)
- std::operator== (memory_resource)
ms.openlocfilehash: dd7dc3e65fe58663285433f9cbc9b64cf2b81cda
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268905"
---
# <a name="ltmemoryresourcegt-operators"></a>&lt;memory_resource&gt; 연산자

## <a name="op_neq"></a> operator!=

연산자의 좌 변에 있는 memory_resource 개체 우변 memory_resource 개체와 같으면 인지 테스트 합니다.

```cpp
template <class T1, class T2>
    bool operator!=(const polymorphic_allocator<T1>& a, const polymorphic_allocator<T2>& b) noexcept;
```

## <a name="op_eq_eq"></a> 연산자 = =

연산자의 좌 변에 있는 memory_resource 개체가 오른쪽에 있는 memory_resource 개체와 같은지 테스트 합니다.

```cpp
template <class T1, class T2>
    bool operator==(const polymorphic_allocator<T1>& a, const polymorphic_allocator<T2>& b) noexcept;
```
