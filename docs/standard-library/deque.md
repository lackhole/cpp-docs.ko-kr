---
title: '&lt;deque&gt;'
ms.date: 11/04/2016
f1_keywords:
- <deque>
helpviewer_keywords:
- deque header
ms.assetid: 4521fe92-5a91-4853-9e9f-59600bf9e46f
ms.openlocfilehash: 145ce22091ea1a42619ad7b1fd25507c6315a9ec
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454493"
---
# <a name="ltdequegt"></a>&lt;deque&gt;

컨테이너 템플릿 클래스 deque 및 다양한 지원 템플릿을 정의합니다.

## <a name="requirements"></a>요구 사항

**헤더**: \<deque>

> [!NOTE]
> Deque \<> 라이브러리는 `#include <initializer_list>` 문을 사용 하기도 합니다.

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[operator!=](../standard-library/deque-operators.md#op_neq)|연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체와 같지 않은지 테스트합니다.|
|[operator<](../standard-library/deque-operators.md#op_lt)|연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 작은지 테스트합니다.|
|[operator\<=](../standard-library/deque-operators.md#op_gt_eq)|연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 작거나 같은지 테스트합니다.|
|[연산자==](../standard-library/deque-operators.md#op_eq_eq)|연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체와 같은지 테스트합니다.|
|[operator>](../standard-library/deque-operators.md#op_gt)|연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 큰지 테스트합니다.|
|[operator>=](../standard-library/deque-operators.md#op_gt_eq)|연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 크거나 같은지 테스트합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[swap](../standard-library/deque-functions.md#swap)|두 deque의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[deque 클래스](../standard-library/deque-class.md)|선형 정렬에서 지정된 형식의 요소를 정렬하고 벡터처럼 모든 요소에 대한 빠른 임의 액세스와 컨테이너 뒤쪽에서 효율적인 삽입 및 삭제를 허용하는 시퀀스 컨테이너의 템플릿 클래스입니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)
