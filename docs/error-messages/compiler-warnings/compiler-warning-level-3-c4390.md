---
title: 컴파일러 경고 (수준 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8402c6a2d0fcbb4704b833ac7ae2b070c7af3a48
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051598"
---
# <a name="compiler-warning-level-3-c4390"></a>컴파일러 경고 (수준 3) C4390

'; ': 제어 되는 빈 문이 있습니다. 이것이 의도 입니까?

명령이 없는 control 문 뒤에 세미콜론이 있습니다.

매크로 때문에 C4390를 가져오는 경우 매크로를 포함 하는 모듈에서 C4390를 사용 하지 않도록 설정 하려면 [warning](../../preprocessor/warning.md) pragma를 사용 해야 합니다.

다음 샘플에서는 C4390를 생성 합니다.

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```