---
title: is_standard_layout 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 4f999eaa4a5c1ea7e9672a5efdc6000a4d3d9759
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457411"
---
# <a name="isstandardlayout-class"></a>is_standard_layout 클래스

형식이 표준 레이아웃인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Ty*|쿼리할 형식입니다.|

## <a name="remarks"></a>설명

이 형식 조건자의 인스턴스는 *Ty* 형식이 메모리에서 멤버 개체의 표준 레이아웃을 포함 하는 클래스인 경우 true이 고 그렇지 않은 경우 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
