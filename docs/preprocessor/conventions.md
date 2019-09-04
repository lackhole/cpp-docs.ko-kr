---
title: 문서 규칙
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- preprocessor, conventions
ms.assetid: 469ce448-dc6c-4d0e-ba2b-e2e7a10155e1
ms.openlocfilehash: bb826b879b71edd3631c11a717320cee51c87175
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220366"
---
# <a name="document-conventions"></a>문서 규칙

규칙은 구문의 여러 구성 요소에 대해 여러 글꼴 특성을 사용합니다. 기호 및 글꼴은 다음과 같습니다.

| 특성 | Description |
|---------------|-----------------|
| *nonterminal* | 기울임꼴은 비터미널을 나타냅니다. |
| **#include** | 굵게 표시된 터미널은 다음과 같이 입력해야 할 리터럴 예약어 및 기호입니다. 이 컨텍스트의 문자는 항상 대/소문자를 구분합니다. |
| <sub>opt</sub> | 뒤에 <sub>opt</sub>가 오는 비터미널은 항상 선택 사항입니다.|
| default typeface | 이 서체에서 설명하거나 나열된 집합의 문자를 C 문의 터미널로 사용될 수 있습니다. |

비터미널 뒤에 오는 콜론( **:** )은 정의를 지정합니다. 다른 정의는 별도의 줄에 나열됩니다.

코드 구문 블록에서 기본 서체의 이러한 기호는 특별 한 의미가 있습니다.

| Symbol | 설명 |
|---|---|
| \[ ] | 대괄호는 선택적 요소를 둘러쌉니다. |
| { \| } | 세로 막대로 구분 된 중괄호 (...)입니다. |
| ... | 이전 요소 패턴을 반복할 수 있음을 나타냅니다. |

코드 구문`,`블록에서 쉼표 (), 마침표 (`.`), 세미 콜론 (`;`), 콜론 (`:`), 괄호 (`( )`), 큰따옴표`"`() 및 작은따옴표 (`'`)는 리터럴입니다.

## <a name="see-also"></a>참고자료

[문법 요약 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)
