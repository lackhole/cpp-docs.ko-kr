---
title: '&lt;stdexcept&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stdexcept>
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
ms.openlocfilehash: d4028d57a6e8898f85a37d9731e7e8d4cda19a2f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453716"
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;

예외 보고에 사용되는 여러 표준 클래스를 정의합니다. 클래스는 [exception](../standard-library/exception-class.md) 클래스에서 모두 파생된 파생 계층 구조를 형성하고 두 가지 일반 형식의 예외(논리 오류 및 런타임 오류)를 포함합니다. 논리 오류는 프로그래머 실수로 인해 발생합니다. 기본 클래스 logic_error에서 파생되며 다음을 포함합니다.

- `domain_error`

- `invalid_argument`

- `length_error`

- `out_of_range`

런타임 오류는 라이브러리 함수 또는 런타임 시스템의 실수로 인해 발생합니다. 기본 클래스 runtime_error에서 파생되며 다음을 포함합니다.

- `overflow_error`

- `range_error`

- `underflow_error`

### <a name="classes"></a>클래스

|클래스|Description|
|-|-|
|[domain_error 클래스](../standard-library/domain-error-class.md)|이 클래스는 도메인 오류를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[invalid_argument 클래스](../standard-library/invalid-argument-class.md)|이 클래스는 잘못된 인수를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[length_error 클래스](../standard-library/length-error-class.md)|이 클래스는 너무 길어서 지정할 수 없는 개체 생성 시도를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[logic_error 클래스](../standard-library/logic-error-class.md)|이 클래스는 논리적 사전 조건 위반과 같이 프로그램이 실행되기 전에 검색될 수 있는 오류를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[out_of_range 클래스](../standard-library/out-of-range-class.md)|이 클래스는 유효 범위를 벗어난 인수를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[overflow_error 클래스](../standard-library/overflow-error-class.md)|이 클래스는 산술 오버플로를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[range_error 클래스](../standard-library/range-error-class.md)|이 클래스는 범위 오류를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[runtime_error 클래스](../standard-library/runtime-error-class.md)|이 클래스는 프로그램이 실행되는 경우에만 검색될 수 있는 오류를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[underflow_error 클래스](../standard-library/underflow-error-class.md)|이 클래스는 산술 언더플로를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
