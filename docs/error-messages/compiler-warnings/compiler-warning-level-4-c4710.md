---
title: 컴파일러 경고(수준 4) C4710
ms.date: 11/04/2016
f1_keywords:
- C4710
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
ms.openlocfilehash: 0f8e66982192f8af6498c9151d32a44226e0560a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395198"
---
# <a name="compiler-warning-level-4-c4710"></a>컴파일러 경고(수준 4) C4710

'function': 함수를 인라이닝 하지 못했습니다

지정된 된 함수를 인라인 확장 선택 했지만 컴파일러가 수행 하지 않은 인라인 처리 합니다.

인라인 처리는 컴파일러의 판단에 따라 수행 됩니다. 합니다 **인라인** 키워드 마찬가지로 합니다 **등록** 키워드를 컴파일러에 대 한 힌트로 사용 됩니다. 컴파일러는 추론을 사용 하 여 여부나 공간 용으로 컴파일할 때 코드를 더 작게 하는 특정 함수를 인라인 할 특정 함수가 속도 용으로 컴파일할 때 코드 속도 인라인 할 경우를 확인할 수 있습니다. 컴파일러는 인라인 매우 작은 기능 공간 용으로 컴파일할 때.

일부 경우에 컴파일러는 인라인 처리 하지 않습니다 특정 함수 기계적 이유로 합니다. 참조 [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) 컴파일러는 함수를 인라인 하지 않는 이유에의 목록은 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.