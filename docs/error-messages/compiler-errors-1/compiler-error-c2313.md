---
title: 컴파일러 오류 C2313
ms.date: 11/04/2016
f1_keywords:
- C2313
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
ms.openlocfilehash: 276dea87770035967a08ca5ac3e95316832ffc1b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344894"
---
# <a name="compiler-error-c2313"></a>컴파일러 오류 C2313

'type1': 참조('type2')에 의해 줄 number에서 catch되었습니다.

예외 형식에 두 개의 처리기가 있습니다. 두 번째 catch에 대한 형식이 첫 번째 형식에 대한 참조입니다.

다음 샘플에서는 C2313을 생성합니다.

```
// C2313.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
    try {
        throw "ooops!";
    }
    catch( C& ) {}
    catch( C ) {}   // C2313
}
```