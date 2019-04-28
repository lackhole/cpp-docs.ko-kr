---
title: noexcept(C++)
ms.date: 01/12/2018
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: c314b554abb6c10e62b143f554777af50267e4e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245363"
---
# <a name="noexcept-c"></a>noexcept(C++)

**C++11:** 함수에서 예외를 throw 할 수 있습니다 있는지 여부를 지정 합니다.

## <a name="syntax"></a>구문

> *noexcept-expression*: &nbsp;&nbsp;&nbsp;&nbsp;**noexcept** &nbsp;&nbsp;&nbsp;&nbsp;**noexcept(** *constant-expression* **)**

### <a name="parameters"></a>매개 변수

*constant-expression*<br/>
형식의 상수 식을 **bool** 잠재적 예외 형식 집합이 비어 있는지 여부를 나타내는입니다. 비 조건부 버전은 `noexcept(true)`합니다.

## <a name="remarks"></a>설명

*noexcept 식* 는 종류의 *예외 사양이*, 접미사를 종료 하는 모든 예외에 대 한 예외 처리기에서 일치 시킬 수 있는 형식 집합을 나타내는 함수 선언에는 함수입니다. 단항 조건부 연산자 `noexcept(` *constant_expression* `)` 여기서 *constant_expression* yeilds **true**, 및 무조건 해당 동의어 **noexcept**, 함수를 종료할 수 있는 잠재적인 예외 형식 집합이 비어 있는지를 지정 합니다. 즉, 함수는 절대 예외를 throw 하 고 해당 범위 외부 전파 예외는 사용할 수 없습니다. 연산자 `noexcept(` *constant_expression* `)` 여기서 *constant_expression* yeilds **false**, 또는 예외 사양이 없는 경우 (이외의 소멸자 또는 할당 해제 함수에 대 한), 모든 형식의 집합 함수를 종료할 수 있는 잠재적인 예외 집합을 나타냅니다.

함수로 표시 **noexcept** 직접 또는 간접적으로 호출한 모든 함수가 이기도 한 경우에 **noexcept** 하거나 **const**합니다. 컴파일러에서 될 수 있는 최대 예외에 대 한 모든 코드 경로 반드시 확인 하지 않습니다는 **noexcept** 함수입니다. 예외가 않습니다 표시 된 함수의 외부 범위를 종료 하는 경우 `noexcept`, [std:: terminate](../standard-library/exception-functions.md#terminate) 가 즉시 호출 이며 모든 범위에서 개체의 소멸자가 호출 되는 보장 되지 않습니다. 사용 하 여 **noexcept** 동적 예외 지정자를 대신 `throw()`에 지원 되지 않는 표준에서입니다. 적용 하는 것이 좋습니다 `noexcept` 모든 함수는 예외가 호출 스택으로 전파 하는 데 사용할 수 없습니다. 함수를 선언 하는 경우 **noexcept**, 다양 한 컨텍스트에서 보다 효율적인 코드를 생성 하도록 컴파일러에 있도록 합니다. 자세한 내용은 [예외 사양](exception-specifications-throw-cpp.md)합니다.

## <a name="example"></a>예제

해당 인수를 복사 하는 템플릿 함수를 선언 될 수 있습니다 **noexcept** 복사 중인 개체가 일반 이전 데이터 형식이 (POD) 조건을 사용 하 여 합니다. 이러한 함수는 다음과 같이 선언될 수 있습니다.

```cpp
#include <type_traits>

template <typename T>
T copy_object(const T& obj) noexcept(std::is_pod<T>)
{
   // ...
}
```

## <a name="see-also"></a>참고자료

[C++ 예외 처리](cpp-exception-handling.md)<br/>
[예외 사양 (throw, noexcept)](exception-specifications-throw-cpp.md)