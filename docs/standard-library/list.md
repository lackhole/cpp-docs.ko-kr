---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
- std::<list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: f2c04bb73bfa379ea87ba4c950bf805931c16ba1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245559"
---
# <a name="ltlistgt"></a>&lt;list&gt;

컨테이너 템플릿 클래스 목록 및 다양한 지원 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <list>
```

> [!NOTE]
> 합니다 \<목록 > 라이브러리 사용을 `#include <initializer_list>` 문입니다.

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[operator!=](../standard-library/list-operators.md#op_neq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체와 같지 않은지 테스트합니다.|
|[operator<](../standard-library/list-operators.md#op_lt)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 작은지 테스트합니다.|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 작거나 같은지 테스트합니다.|
|[연산자==](../standard-library/list-operators.md#op_eq_eq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체와 같은지 테스트합니다.|
|[operator>](../standard-library/list-operators.md#op_gt)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 큰지 테스트합니다.|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 크거나 같은지 테스트합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[swap](../standard-library/list-functions.md#swap)|두 목록의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[list 클래스](../standard-library/list-class.md)|선형 배열에서 해당 요소를 유지 관리하고 시퀀스 내 모든 위치에서 효율적인 삽입과 삭제를 수행할 수 있도록 하는 시퀀스 컨테이너의 템플릿 클래스입니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
