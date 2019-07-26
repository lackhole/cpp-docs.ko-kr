---
title: is_literal_type 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: 450c32d050a18f64e71992bd7a30412ebafe93de
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456220"
---
# <a name="isliteraltype-class"></a>is_literal_type 클래스

형식을 `constexpr` 변수로 사용하거나, `constexpr` 함수에서 생성, 사용 또는 반환할 수 있는지를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>매개 변수

*트*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *T* 형식이 *리터럴 형식이*면 true이 고, 그렇지 않으면 false입니다. 리터럴 형식은 **void**, 스칼라 형식, 참조 형식, 리터럴 형식의 배열 또는 리터럴 클래스 형식 중 하나입니다. 리터럴 클래스 형식은 trivial 소멸자가 있거나, 집계 형식이거나, 이동하거나 복사할 수 없는 하나 이상의 `constexpr` 생성자가 있는 클래스 형식이며 모든 기본 클래스 및 비정적 데이터 멤버는 비휘발성 리터럴 형식입니다. literal의 형식은 항상 리터럴 형식이지만 리터럴 형식의 개념에는 컴파일러가 컴파일 시간에 `constexpr`로 평가할 수 있는 모든 항목이 포함됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
