---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: f3b4896a3cb4774e46b36480dd9769fa131fc287
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957172"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

컨테이너 템플릿 클래스 `optional` 및 다양한 지원 템플릿을 정의합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<선택적 >

**네임스페이스:** std

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자==](../standard-library/optional-operators.md#op_eq_eq)|개체가 다른 개체와 같은지 여부를 테스트 합니다.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|개체가 다른 개체와 같지 않은 지 테스트 합니다.|
|[operator<](../standard-library/optional-operators.md#op_lt)|왼쪽의 개체가 오른쪽에 있는 개체 보다 작음을 테스트 합니다.|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|왼쪽의 개체가 오른쪽에 있는 개체 보다 작거나 같은지 테스트 합니다.|
|[operator>](../standard-library/optional-operators.md#op_gt)|왼쪽의 개체가 오른쪽에 있는 개체 보다 큰지 테스트 합니다.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|왼쪽의 개체가 오른쪽에 있는 개체 보다 크거나 같은지 테스트 합니다.|

> [!NOTE]
> 선택적 > 연산자는 \<관계형 비교 외에도 **nullopt** 및 `T`와의 비교를 지원 합니다.

### <a name="functions"></a>함수

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|개체를 선택적으로 만듭니다.|
|[swap](../standard-library/optional-functions.md#swap)|두 `optional` 개체의 포함 된 값을 바꿉니다.|

### <a name="classes-and-structs"></a>클래스 및 구조체

|||
|-|-|
|hash|포함 된 개체의 해시를 반환 합니다.|
|[선택적 클래스](../standard-library/optional-class.md)|값을 포함 하거나 포함 하지 않을 수 있는 개체에 대해 설명 합니다.|
|[nullopt_t 구조체](../standard-library/nullopt-t-structure.md)|값을 포함 하지 않는 개체에 대해 설명 합니다.|
|[bad_optional_access 클래스](../standard-library/bad-optional-access-class.md)|없는 값에 대 한 액세스 시도를 보고 하기 위해 예외로 throw 되는 개체에 대해 설명 합니다.|

### <a name="objects"></a>개체

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|비교할의 `nullopt_t` 인스턴스입니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
