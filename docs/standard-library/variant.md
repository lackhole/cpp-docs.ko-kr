---
title: '&lt;Variant&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 7a812ccc3c8cb2a660c01ad2b17ea75b5d5c9542
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268445"
---
# <a name="ltvariantgt"></a>&lt;Variant&gt;

Variant 개체를 보유 하 고 값을 관리 합니다. 변형 값을 갖는 경우 해당 값의 형식은 변형에 지정 된 템플릿 인수 형식 중 하나 여야 합니다. 이러한 템플릿 인수 대안 이라고 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<variant >

**네임스페이스:** std

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자==](../standard-library/forward-list-operators.md#op_eq_eq)|연산자의 좌 변에 있는 variant 개체 오른쪽에 있는 변형 개체와 같은지 테스트 합니다.|
|[operator!=](../standard-library/forward-list-operators.md#op_neq)|연산자의 좌 변에 있는 variant 개체 오른쪽에 있는 변형 개체와 같으면 인지 테스트 합니다.|
|[operator<](../standard-library/forward-list-operators.md#op_lt)|Variant 연산자의 좌 변에 있는 개체가 우변에 있는 variant 개체 보다 작은지 테스트 합니다.|
|[operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|연산자의 좌 변에 있는 개체가 변형 테스트 보다 작거나 변형 개체에 오른쪽에 있는 경우|
|[operator>](../standard-library/forward-list-operators.md#op_gt)|연산자의 좌 변에 있는 변형 개체가 오른쪽에 variant 개체 보다 큰지 테스트 합니다.|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|Variant 연산자의 좌 변에 있는 개체가 우변에 있는 variant 개체 보다 크거나 하는지 테스트 합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[get](../standard-library/variant-functions.md#get)|개체의 변형을 가져옵니다.|
|[get_if](../standard-library/variant-functions.md#get_if)|있는 경우 개체의 변형을 가져옵니다.|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|반환 **true** 변형이 있는 경우.|
|[swap](../standard-library/variant-functions.md#swap)|교환 된 **변형**합니다.|
|[방문](../standard-library/variant-functions.md#visit)|다음으로 이동 **변형**합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Variant 개체의 값에 잘못 된 액세스를 보고서에 throw 되는 개체입니다.|
|[Variant](../standard-library/variant.md)|개체 중 하나를 해당 대체 형식 중 하나 또는 값의 값을 저장 합니다.|

### <a name="structs"></a>구조체

|||
|-|-|
|[hash](../standard-library/hash-structure.md)||
|[monostate](../standard-library/monostate-structure.md)|다른 형식 변형에 대 한 변형 형식은 기본 형식이 되도록입니다.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Variant 개체를 지원합니다.|
|[variant_size](../standard-library/variant-size-structure.md)|Variant 개체를 지원합니다.|

### <a name="objects"></a>개체

|||
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
