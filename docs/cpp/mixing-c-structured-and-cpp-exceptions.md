---
title: 혼합 C (구조적) 및 C++ 예외
ms.date: 08/14/2018
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 94d6dc249cb130aaf09d3202b9e8f437d00a9597
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345962"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>혼합 C (구조적) 및 C++ 예외

구조적 예외 처리 (SEH)를 사용 이식 가능한 코드를 작성 하려는 경우는 C++ 프로그램을 권장 하지 않습니다. 그러나 사용 하 여 컴파일하고 하려는 경우에 따라 [/EHa](../build/reference/eh-exception-handling-model.md) 구조화 된 예외를 혼합 및 및 C++ 소스 코드 및 두 종류의 예외를 처리 하기 위한 일부 기능이 필요 합니다. throw 된 예외를 처리할 수 없는 구조적된 예외 처리기 개체 또는 형식화 된 예외의 개념이 있어 C++ 코드입니다. 그러나 C++ **catch** 처리기는 구조화 된 예외를 처리할 수 있습니다. C++예외 처리 구문을 (**시도**, **throw**하십시오 **catch**)는 C 컴파일러의 경우 구조적된 예외 처리 구문을에서 허용 되지 않습니다 (**__try**, **__except**, **__finally**)에서 지원 되는 C++ 컴파일러.

참조 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) 구조화 된 예외를 처리 하는 방법에 대 한 정보에 대 한 C++ 예외입니다.

구조적를 함께 사용할 경우 및 C++ 예외를 이러한 잠재적인 문제에 유의 합니다.

- C++ 예외 및 구조화된 예외는 동일한 함수 내에서 혼합될 수 없습니다.

- 종료 처리기 (**__finally** 블록) 예외가 throw 된 후 해제 하는 동안에 항상 실행 됩니다.

- C++예외 처리를 catch 할 수 및 preserve로 컴파일된 모든 모듈의 의미 체계를 해제 합니다 [/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 해제 의미 체계는 사용 합니다.

- 소멸자 함수가 모든 개체에 대해 호출하지 않는 일부 경우가 있을 수 있습니다. 예를 들어, 함수는 초기화 되지 않은 함수 포인터를 통해 호출 하는 동안 구조화 된 예외를 발생 하는 경우 해당 함수 호출 전에 생성 된 매개 변수 개체는 해당 개체의 소멸자가 호출 되지 않습니다. 중 스택 해제 합니다.

## <a name="next-steps"></a>다음 단계

- [Setjmp 또는 longjmp에서 사용 하 여 C++ 프로그램](../cpp/using-setjmp-longjmp.md)

  사용에 대 한 자세한 내용은 `setjmp` 하 고 `longjmp` 에서 C++ 프로그램입니다.

- [C++에서 구조적 예외 처리](../cpp/exception-handling-differences.md)

  사용할 수 있는 방법의 예를 보려면 C++ 구조화 된 예외를 처리할 수 있습니다.

## <a name="see-also"></a>참고자료

[C++ 예외 처리](../cpp/cpp-exception-handling.md)
