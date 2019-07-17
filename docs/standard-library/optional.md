---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: c73ad2ad94a5de29bc2c457fdf6ca8b9c783615c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268485"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

선택적 컨테이너 템플릿 클래스 및 여러 지원 템플릿을 정의합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<옵션 >

**네임스페이스:** std

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자==](../standard-library/optional-operators.md#op_eq_eq)|연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체와 같은지 테스트합니다.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체와 같지 않은지 테스트합니다.|
|[operator<](../standard-library/optional-operators.md#op_lt)|연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 작은지 테스트합니다.|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 작거나 같은지 테스트합니다.|
|[operator>](../standard-library/optional-operators.md#op_gt)|연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 큰지 테스트합니다.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 크거나 같은지 테스트합니다.|

> [!NOTE]
> 관계형 비교 하는 것 외에도 \<선택 사항 > 연산자에 사용 하 여 비교도 지원 **nullopt** 고 `T`입니다.

### <a name="functions"></a>함수

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|옵션 개체를 만듭니다.|
|[swap](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>클래스 및 구조체

|||
|-|-|
|[hash]()||
|[선택적 클래스](../standard-library/optional-class.md)|수도 있고 값이 적용 되지 않을 수도 있는 개체를 설명 합니다.|
|[nullopt_t 구조체](../standard-library/nullopt-t-structure.md)|값을 보유 하지 개체를 설명 합니다.|
|[bad_optional_access 클래스](../standard-library/bad-optional-access-class.md)|보고 되지 있습니다 값에 액세스 하려고 예외로 throw 하는 개체를 설명 합니다.|

### <a name="objects"></a>개체

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
