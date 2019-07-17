---
title: '&lt;set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <set>
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
ms.openlocfilehash: 1bf5663d3e6891d45e2139c612d8e16860b6cace
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246378"
---
# <a name="ltsetgt"></a>&lt;set&gt;

컨테이너 템플릿 클래스 set 및 multiset과 지원 템플릿을 정의합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<set>

**네임스페이스:** std

> [!NOTE]
> 합니다 \<설정 > 라이브러리 사용을 `#include <initializer_list>` 문입니다.

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|set 버전|multiset 버전|설명|
|-|-|-|
|[operator!= (set)](../standard-library/set-operators.md#op_neq)|[operator!= (multiset)](../standard-library/set-operators.md#op_neq)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체와 같지 않은지 테스트합니다.|
|[operator< (set)](../standard-library/set-operators.md#op_lt)|[operator< (multiset)](../standard-library/set-operators.md#op_lt_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 작은지 테스트합니다.|
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 작거나 같은지 테스트합니다.|
|[operator== (set)](../standard-library/set-operators.md#op_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체와 같은지 테스트합니다.|
|[operator> (set)](../standard-library/set-operators.md#op_gt)|[operator> (multiset)](../standard-library/set-operators.md#op_gt_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 큰지 테스트합니다.|
|[operator>= (set)](../standard-library/set-operators.md#op_gt_eq)|[operator>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 크거나 같은지 테스트합니다.|

### <a name="specialized-template-functions"></a>특별 템플릿 함수

|set 버전|multiset 버전|Description|
|-|-|-|
|[swap](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|두 set 또는 multiset의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[set 클래스](../standard-library/set-class.md)|포함된 요소의 값이 고유하고 데이터가 자동 정렬되는 기준인 키 값으로 사용된 컬렉션의 데이터를 저장 및 검색하는 데 사용됩니다.|
|[multiset 클래스](../standard-library/multiset-class.md)|포함된 요소의 값이 고유할 필요가 없고 데이터가 자동 정렬되는 기준인 키 값으로 사용된 컬렉션의 데이터를 저장 및 검색하는 데 사용됩니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
