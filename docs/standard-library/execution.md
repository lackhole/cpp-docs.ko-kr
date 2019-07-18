---
title: '&lt;실행&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 3bce34019f9ed4880d72a9d16c3c8b78dde0e0e3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268425"
---
# <a name="ltexecutiongt"></a>&lt;실행&gt;

병렬 알고리즘에 대 한 실행 정책을 설명합니다.

## <a name="syntax"></a>구문

```
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```
### <a name="classes-and-structs"></a>클래스 및 구조체

|||
|-|-|
|[is_execution_policy 구조체](is-execution-policy-struct.md)|함수 시그니처를 제외 하 고 그렇지 않은 경우 모호한 오버 로드 확인 참가 하기 위해 실행 정책을 검색 합니다.|
|[parallel_policy 클래스](parallel-policy-class.md)|고유 형식으로 병렬 알고리즘 오버 로드 명확 하 게 병렬 알고리즘의 실행을 병렬 처리할 수를 표시 하는 데 사용 합니다.|
|[parallel_unsequenced_policy 클래스](parallel-unsequenced-policy-class.md)|병렬 알고리즘 오버 로드를 명확히 구분 하는 병렬 알고리즘의 실행은 병렬 처리 되 고 벡터화 있습니다 나타내려면 고유 형식으로 사용 합니다.|
|[sequenced_policy 클래스](sequenced-policy-class.md)|고유 형식으로 병렬 알고리즘 오버 로드를 명확히 구분 해야 병렬 알고리즘을 실행을 병렬 처리할 수 있습니다 하는 데 사용 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<실행 >

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[헤더 파일 참조](cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](cpp-standard-library-reference.md)
