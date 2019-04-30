---
title: '&lt;system_error&gt;'
ms.date: 03/15/2019
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: 9bba893f63ca935e0feeb891faa4e141e1958306
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412100"
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;

헤더를 포함 \<system_error > 예외 클래스를 정의 하려면 `system_error` 및 관련 템플릿을 하위 수준 시스템 오류를 처리 합니다.

## <a name="syntax"></a>구문

```cpp
#include <system_error>
```

### <a name="objects"></a>개체

|||
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|일반 오류의 범주를 나타냅니다.|
|[system_category](../standard-library/system-error-functions.md#system_category)|하위 수준 시스템 오버플로로 인해 발생하는 오류의 범주를 나타냅니다.|

### <a name="functions"></a>함수

|기능|설명|
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|`error_code` 개체를 만듭니다.|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|`error_condition` 개체를 만듭니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[연산자==](../standard-library/system-error-operators.md#op_eq_eq)|연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.|
|[operator!=](../standard-library/system-error-operators.md#op_neq)|연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.|
|[operator<](../standard-library/system-error-operators.md#op_lt)|개체가 비교를 위해 전달된 개체보다 작은지 여부를 테스트합니다.|

### <a name="enumerations"></a>열거형

|||
|-|-|
|[errc](../standard-library/system-error-enums.md#errc)|`<errno.h>`에서 Posix에 의해 정의된 모든 오류 코드 매크로에 대해 기호화된 이름을 제공합니다.|

### <a name="classes-and-structs"></a>클래스 및 구조체

|||
|-|-|
|[error_category](../standard-library/error-category-class.md)|오류 코드 범주를 설명하는 개체에 대한 추상, 공통 기본을 나타냅니다.|
|[error_code](../standard-library/error-code-class.md)|구현에 관련된 하위 수준 시스템 오류를 나타냅니다.|
|[error_condition](../standard-library/error-condition-class.md)|사용자 정의 오류 코드를 나타냅니다.|
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|[error_code 클래스](../standard-library/error-code-class.md) 열거형을 테스트하는 형식 조건자를 나타냅니다.|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|[error_condition 클래스](../standard-library/error-condition-class.md) 열거형을 테스트하는 형식 조건자를 나타냅니다.|
|[system_error](../standard-library/system-error-class.md)|하위 수준 시스템 오버플로를 보고하기 위해 throw되는 모든 예외에 대한 기본 클래스를 나타냅니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<system_error>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
