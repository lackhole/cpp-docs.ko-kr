---
title: 컴파일러 오류 C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: bd056a63ab60cd5a2504c6a0bc19e388f71b068b
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450060"
---
# <a name="compiler-error-c3872"></a>컴파일러 오류 C3872

'char': 식별자에는 이 문자를 사용할 수 없습니다.

C++ 컴파일러는 식별자에서 허용되는 문자에 대한 C++11 표준을 따릅니다. 특정 범위의 문자와 유니버설 문자 이름만 식별자에서 허용됩니다. 식별자의 시작 문자에는 추가 제한이 적용됩니다. 자세한 내용 및 허용되는 문자 목록과 유니버설 문자 이름 범위는 [Identifiers](../../cpp/identifiers-cpp.md)를 참조하세요.

식별자에서 허용되는 문자의 범위는 C++/CLI 코드를 컴파일하는 경우보다 덜 제한적입니다. /Clr을 사용 하 여 컴파일된 코드의 식별자 따라야 [표준 ECMA-335: Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm)합니다.

다음 샘플에서는 C3872를 생성합니다.

```
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```