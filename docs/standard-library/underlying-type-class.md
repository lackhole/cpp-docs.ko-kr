---
title: underlying_type 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: 465383357e6c0306c24fe8325327327c3a3b64c1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454982"
---
# <a name="underlyingtype-class"></a>underlying_type 클래스

열거형 형식에 대한 내부 정수 계열 형식을 생성합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>매개 변수

*트*\
수정할 형식입니다.

## <a name="remarks"></a>설명

T `type` 가 열거형 형식인 경우 템플릿 클래스의 멤버 typedef는 *t*의 기본 정수 계열  형식 이름을, 그렇지 않으면 멤버 typedef `type`가 없습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
