---
title: Setjmp 및 longjmp 사용
ms.date: 08/14/2018
f1_keywords:
- longjmp_cpp
- setjmp_cpp
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
ms.openlocfilehash: 4ead12f79701899b3977993c9de3c3803023150f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364521"
---
# <a name="using-setjmp-and-longjmp"></a>Setjmp 및 longjmp 사용

때 [setjmp](../c-runtime-library/reference/setjmp.md) 하 고 [longjmp](../c-runtime-library/reference/longjmp.md) 는 로컬이 아닌를 실행 하는 방법을 제공 함께 사용 하는 **goto**합니다. 이러한 표준 호출을 사용 하지 않고 전에 호출된 된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달할 C 코드에서 일반적으로 사용 되 나 반환 규칙.

> [!CAUTION]
> 때문에 `setjmp` 하 고 `longjmp` 간단 하 게 해당 사이의 올바른 스택 프레임 개체 소멸을 지원 하지 않습니다 C++ 컴파일러에서 사용 되는 권장 하지 지역 변수의 최적화를 막아 성능을 저하 시킬 수 있으므로, C++ 프로그램입니다. 사용 하는 것이 좋습니다 **시도** 하 고 **catch** 대신 생성 합니다.

사용 하려는 경우 `setjmp` 하 고 `longjmp` 에 C++ 프로그램을 포함할 수도 \<setjmp.h > 또는 \<setjmpex.h > 함수와 구조적 예외 처리 (SEH) 간에 올바른 상호 작용이 수행 하기 위해 또는 C++ 예외 처리 합니다.

**Microsoft 전용**

사용 하는 경우는 [/EH](../build/reference/eh-exception-handling-model.md) 컴파일하는 옵션을 C++ , 소멸자에 대 한 코드의 스택 해제 중 로컬 개체 라고 합니다. 그러나 사용 하는 경우 **/EHs** 하거나 **/EHsc** 컴파일 및 사용 하는 함수 중 하나를 [noexcept](../cpp/noexcept-cpp.md) 호출 `longjmp`, 해당 함수에 대 한 소멸자를 해제 한 다음 최적화 프로그램 상태에 따라, 발생할 수 있습니다.

이식 가능한 코드의 경우는 `longjmp` 호출이 실제로 실행을 잘못 프레임 기반 개체가 소멸은 명시적으로 반드시 표준 및 다른 컴파일러에서 지원 되지 않습니다. 경고 수준 4에서 호출을 알 수 있도록 `setjmp` C4611 경고를 발생: 'j 간의 상호 작용 하 고 C++ 개체 소멸 이식 가능 하지 않습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[C(구조적) 및 C++ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)
