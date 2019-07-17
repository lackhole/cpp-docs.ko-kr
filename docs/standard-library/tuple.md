---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: ce6e005990d05676fb20752b5808d32ec88dd7b3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241547"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

해당 인스턴스에 다양한 형식의 개체가 포함된 `tuple` 템플릿을 정의합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<tuple>

**네임스페이스:** std

## <a name="members"></a>멤버

### <a name="classes-and-structs"></a>클래스 및 구조체

|||
|-|-|
|[tuple 클래스](../standard-library/tuple-class.md)|고정 길이의 요소 시퀀스를 래핑합니다.|
|[tuple_element 클래스](../standard-library/tuple-element-class-tuple.md)|`tuple` 요소의 형식을 래핑합니다.|
|[tuple_size 클래스](../standard-library/tuple-size-class-tuple.md)|`tuple` 요소 개수를 래핑합니다.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||

### <a name="objects"></a>개체

|||
|-|-|
|[tuple_element_t](../standard-library/tuple-functions.md#tuple_element_t)||
|[tuple_size_v](../standard-library/tuple-functions.md#tuple_size_v)||

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자==](../standard-library/tuple-operators.md#op_eq_eq)|비교 `tuple` 같은 개체입니다.|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|비교 `tuple` 같지 않은 개체입니다.|
|[operator<](../standard-library/tuple-operators.md#op_lt)|비교 `tuple` 개체 보다 작습니다.|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|비교 `tuple` 보다 작거나 같은 개체입니다.|
|[operator>](../standard-library/tuple-operators.md#op_gt)|비교 `tuple` 개체 보다 큽니다.|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|비교 `tuple` 보다 크거나 같은 개체입니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[apply](../standard-library/tuple-functions.md#apply)|튜플 사용 하 여 함수를 호출합니다.|
|[forward_as_tuple](../standard-library/tuple-functions.md#forward)|참조의 튜플을 만듭니다.|
|[get](../standard-library/tuple-functions.md#get)|`tuple` 개체에서 요소를 가져옵니다.|
|[make_from_tuple](../standard-library/tuple-functions.md#make_from_tuple)|확인 하는 줄임을 `tuple`입니다.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|요소 값에서 `tuple`을 만듭니다.|
|[swap](../standard-library/tuple-functions.md#swap)||
|[tie](../standard-library/tuple-functions.md#tie)|요소 선언에서 `tuple`을 만듭니다.|
|[tuple_cat](../standard-library/tuple-functions.md#tuple_cat)|형식 요소의 범위를 사용 하 여 튜플 개체를 생성합니다.|

## <a name="see-also"></a>참고자료

[\<array>](../standard-library/array.md)<br/>
