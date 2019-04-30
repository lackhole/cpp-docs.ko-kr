---
title: is_standard_layout 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 75691c1b09b71580474cc22cdc8382bff55a5e29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413504"
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

이 형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 는 클래스 멤버 개체의 표준 레이아웃에는 메모리, 그렇지 않으면 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
