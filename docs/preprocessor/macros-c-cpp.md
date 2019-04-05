---
title: 매크로 (C/C++)
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
ms.openlocfilehash: 281aaf686c07894b5cb1fab187ba903179c51de8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032182"
---
# <a name="macros-cc"></a>매크로 (C/C++)
전처리기 지시문에 없는 모든 줄의 매크로 확장을 전처리 (되지 않은 줄을 **#** 첫 번째 공백이 아닌 문자) 및 일부 지시문의 일부로 건너뛰지 않습니다는 조건부 컴파일입니다. "조건부 컴파일" 지시문을 사용하면 상수 식을 테스트하여 소스 파일의 일부 컴파일을 억제하거나 식별자를 사용하여 전처리 과정에서 어떤 텍스트 블록이 컴파일러에 전달되고 어떤 텍스트 블록이 소스 파일에서 제거되는지 결정할 수 있습니다.

`#define` 지시문은 일반적으로 의미 있는 식별자와 자음, 키워드, 자주 사용되는 명령문 또는 수식과 연결하는 데 사용합니다. 상수를 나타내는 식별자는 "기호화된 상수" 또는 "매니페스트 상수"라고도 합니다. 문 또는 식을 나타내는 식별자는 "매크로"라고 합니다. 이 전처리기 설명서에서는 "매크로" 용어만 사용됩니다.

프로그램 소스 텍스트 또는 다른 특정 전처리기 명령 인수에 매크로의 이름이 인식되면, 해당 매크로에 대한 호출로 처리됩니다. 매크로 이름은 매크로 본문의 복사본으로 교체됩니다. 매크로에서 인수를 수락할 경우 매크로 이름 다음의 실제 인수가 매크로 본문의 정식 매개 변수 대신 사용됩니다. 본문의 복사본으로 매크로 호출을 대신하는 프로세스를 매크로 호출의 "확장"이라고 합니다.

실질적으로 두 가지 유형의 매크로가 있습니다. "개체와 유사한" 매크로는 인수를 사용하지 않지만 "함수와 유사한" 매크로는 함수 호출처럼 보이고 작동하기 위해 인수를 받아들이도록 정의될 수 있습니다. 매크로는 실제 함수 호출을 생성하지 않으므로 때로는 함수 호출을 매크로로 바꾸어 프로그램을 더 빠르게 실행할 수 있습니다. C++에서 인라인 함수는 흔히 기본 설정 메서드입니다. 하지만 매크로를 정의하지 않을 경우 문제가 될 수 있으므로 신중하게 사용해야 합니다. 괄호 안에 인수를 갖는 매크로 정의의 식에 적절한 우선 순위를 유지하기 위해 사용할 수 있습니다. 또한 매크로는 파생 작업이 있는 식을 올바르게 처리할 수 없습니다. 참조를 `getrandom` 에서 예제 [는 #define 지시문](../preprocessor/hash-define-directive-c-cpp.md) 자세한 내용은 합니다.

매크로를 정의한 후에 다른 값으로 원래 정의를 먼저 분리하지 않고 재정의할 수 없습니다. 하지만 매크로를 정확히 동일한 정의로 재정의할 수 있습니다. 따라서 동일한 정의가 프로그램에서 한 번 이상 나타날 수 있습니다.

`#undef` 지시문이 매크로의 정의 제거 합니다. 정의를 제거한 한 후에 매크로에 다른 값을 재정의할 수 있습니다. [#define 지시문](../preprocessor/hash-define-directive-c-cpp.md) 및 [#undef 지시문](../preprocessor/hash-undef-directive-c-cpp.md) 에 대해 설명 합니다 `#define` 및 `#undef` 지시문을 각각.

자세한 내용은 다음 항목을 참조하세요.

- [매크로 및 C++](../preprocessor/macros-and-cpp.md)

- [가변 매크로](../preprocessor/variadic-macros.md)

- [미리 정의된 매크로](../preprocessor/predefined-macros.md)

## <a name="see-also"></a>참고자료

[C/C++ 전처리기 도움말](../preprocessor/c-cpp-preprocessor-reference.md)