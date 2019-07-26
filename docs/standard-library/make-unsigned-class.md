---
title: make_unsigned 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 4c0224bd5fd7dc8c6589ae474bb9acb9a8f09cf6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456319"
---
# <a name="makeunsigned-class"></a>make_unsigned 클래스

형식을 만들거나 형식의 크기보다 크거나 같은 부호가 없는 가장 작은 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*T*|수정할 형식입니다.|

## <a name="remarks"></a>설명

형식 한정자의 인스턴스는가 true 인 경우 `is_unsigned<T>` *T* 인 수정 된 형식을 보유 합니다. 그렇지 않은 경우 가장 작은 부호 있는 형식 `ST`이며, 여기서 `sizeof (T) <= sizeof (ST)`입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
