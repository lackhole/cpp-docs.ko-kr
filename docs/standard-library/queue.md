---
title: '&lt;queue&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: 641ab1bfe99360320509b806149fcedfe1068879
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240358"
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

템플릿 클래스 priority_queue와 큐 및 여러 지원 템플릿을 정의합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<queue>

**네임스페이스:** std

> [!NOTE]
> 합니다 \<큐 > 라이브러리 사용을 `#include <initializer_list>` 문입니다.

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[operator!=](../standard-library/queue-operators.md#op_neq)|연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체와 같지 않은지 테스트합니다.|
|[operator<](../standard-library/queue-operators.md#op_lt)|연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 작은지 테스트합니다.|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 작거나 같은지 테스트합니다.|
|[연산자==](../standard-library/queue-operators.md#op_eq_eq)|연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체와 같은지 테스트합니다.|
|[operator>](../standard-library/queue-operators.md#op_gt)|연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 큰지 테스트합니다.|
|[operator>=](../standard-library/queue-operators.md#op_gt_eq)|연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 크거나 같은지 테스트합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[swap]()||

### <a name="classes"></a>클래스

|||
|-|-|
|[queue 클래스](../standard-library/queue-class.md)|일부 기본 컨테이너 형식의 앞과 뒤 요소에 대한 액세스를 제한하는 기능 제한을 제공하는 템플릿 컨테이너 어댑터 클래스입니다.|
|[priority_queue 클래스](../standard-library/priority-queue-class.md)|항상 가장 큰 일부 기본 컨테이너 형식의 최상위 요소에 대한 액세스를 제한하는 기능 제한을 제공하는 템플릿 컨테이너 어댑터 클래스입니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
