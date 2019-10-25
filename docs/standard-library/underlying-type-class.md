---
title: underlying_type 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: ea4768d78047112a7584ca49b0e4487fad55a970
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688838"
---
# <a name="underlying_type-class"></a>underlying_type 클래스

열거형 형식에 대한 내부 정수 계열 형식을 생성합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>매개 변수

*T* \
수정할 형식입니다.

## <a name="remarks"></a>주의

클래스 템플릿의 `type` 멤버 typedef *는 t가 열거형 형식일 때* *t*의 기본 정수 계열 형식에 이름을, 그렇지 않으면 멤버 typedef `type` 없습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참조

[<type_traits>](../standard-library/type-traits.md)
