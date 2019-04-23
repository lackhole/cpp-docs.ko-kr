---
title: 매크로 및 C++
ms.date: 11/04/2016
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: d4915526d5bb84b33f0595678781257d754aaf2d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024918"
---
# <a name="macros-and-c"></a>매크로 및 C++
C++는 새로운 기능을 제공하며 그 중 일부는 ANSI C 전처리기에서 제공하는 기능을 대신합니다. 이 새로운 기능으로 형식이 더욱 안전해지고 효과적으로 언어를 예측할 수 있습니다.

- C++로 선언 된 개체 **const** 상수 식에서 사용할 수 있습니다. 형식 및 값 정보가 있는 상수와 디버거에서 기호로 표시된 열거형이 있는 상수를 프로그램에서 선언할 수 있습니다. 전처리기 `#define` 지시문을 사용하여 상수를 정의하는 것으로는 충분하지 않습니다. 에 대 한 저장소 할당 되는 **const** 프로그램에서 해당 주소를 사용 하는 식 없으면 개체입니다.

- C ++ 인라인 함수 기능은 함수 형식 매크로를 대신합니다. 인라인 함수를 사용하면 매크로에 비해 다음과 같은 이점이 있습니다.

    - 형식 안전성. 인라인 함수는 일반 함수와 똑같은 함수 검사를 받습니다. 매크로는 형식이 안전하지 않습니다.

    - 의도하지 않은 결과가 생기는 인수를 올바르게 처리. 인라인 함수는 함수 본문을 입력하기 전에 식을 인수로 계산하므로 의도하지 않은 결과를 가진 식이 안전성을 유지할 수 있습니다.

인라인 함수에 대 한 자세한 내용은 참조 하세요. [인라인, __inline \__forceinline](../cpp/inline-functions-cpp.md)합니다.

이전 버전과의 호환성을 위해 ANSI C 및 이전의 C++ 사양에 있는 모든 전처리기 기능이 Microsoft C++에 대해 유지됩니다.

## <a name="see-also"></a>참고자료

[미리 정의된 매크로](../preprocessor/predefined-macros.md)<br/>
[매크로(C/C++)](../preprocessor/macros-c-cpp.md)