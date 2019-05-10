---
title: make_unsigned 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 42c722c5250a4989b930d8f1e6fe52f2eccc614a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413049"
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

|매개 변수|설명|
|---------------|-----------------|
|*T*|수정할 형식입니다.|

## <a name="remarks"></a>설명

형식 수정자의 인스턴스는 수정 된 형식인 됩니다 *T* 경우 `is_unsigned<T>` 마찬가지입니다. 그렇지 않은 경우 가장 작은 부호 있는 형식 `ST`이며, 여기서 `sizeof (T) <= sizeof (ST)`입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
