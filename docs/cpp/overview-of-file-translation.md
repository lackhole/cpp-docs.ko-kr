---
title: 파일 변환 개요
ms.date: 11/04/2016
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
ms.openlocfilehash: cb8a8fea2411e4eb7de78545f70021f3617b0f52
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325145"
---
# <a name="overview-of-file-translation"></a>파일 변환 개요

C 프로그램과 같은 C++ 프로그램은 하나 이상의 파일로 구성됩니다. 이러한 각 파일은 다음 개념적 순서로 변환됩니다. 실제 순서는 "as if" 규칙을 따릅니다. 변환은 이러한 단계를 수행한 것처럼 발생해야 합니다.

1. 어휘 토큰화. 문자 매핑 및 삼중자 처리, 줄 스플라이스 및 토큰화는 이 변환 단계에서 수행됩니다.

1. 전처리. 이 변환 단계에서 참조 하는 보조 소스 파일에는 `#include` 지시문을 "stringizing" 및 "charizing" 지시문을 처리 하 고 토큰 붙여넣기 및 매크로 확장을 수행 (참조 [전처리기 지시문](../preprocessor/preprocessor-directives.md) 에 *전처리기 참조* 자세한). 전처리 단계의 결과는 함께 "변환 단위"를 정의하는 토큰 시퀀스입니다.

   전처리기 지시문은 항상 숫자 기호를 사용 하 여 시작 (**#**) 문자 (즉, 줄에서 첫 번째 공백이 아닌 문자 여야 함 숫자 기호). 하나의 전처리기 지시문만 지정된 줄에 나타날 수 있습니다. 예를 들어:

    ```cpp
    #include <iostream>  // Include text of iostream in
                         //  translation unit.
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty
                         //  text string).
    ```

1. 코드 생성. 이 변환 단계는 전처리 단계에서 생성된 토큰을 사용하여 개체 코드를 생성합니다.

   이 단계 중 소스 코드의 구문 및 의미 체계 검사가 수행됩니다.

참조 [변환 단계](../preprocessor/phases-of-translation.md) 에 *전처리기 참조* 자세한 내용은 합니다.

C++ 전처리기는 ANSI C 전처리기의 엄격한 상위 집합이지만 몇 가지 점에서 다릅니다. 다음 목록에서는 ANSI C 전처리기와 C++ 전처리기의 여러 가지 차이점을 설명합니다.

- 한 줄로 된 주석이 지원됩니다. 참조 [주석을](../cpp/comments-cpp.md) 자세한 내용은 합니다.

- 미리 정의 된 매크로인 `__cplusplus`에 대해서만 정의 되며 C++합니다. 참조 [미리 정의 된 매크로](../preprocessor/predefined-macros.md) 에 *전처리기 참조* 자세한 내용은 합니다.

- C 전처리기 인식 하지 않습니다는 C++ 연산자: **합니다.** <strong>\*</strong>하십시오 **->** <strong>\*</strong>, 및 **::** 합니다. 참조 [연산자](../cpp/cpp-built-in-operators-precedence-and-associativity.md) 하 고 [식을](../cpp/expressions-cpp.md), 연산자에 대 한 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[어휘 규칙](../cpp/lexical-conventions.md)
