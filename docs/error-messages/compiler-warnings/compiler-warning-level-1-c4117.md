---
title: 컴파일러 경고(수준 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 97fd5703a744448db87634e313678cf4e824df7f
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626283"
---
# <a name="compiler-warning-level-1-c4117"></a>컴파일러 경고(수준 1) C4117

'name' 매크로 이름이 예약되었습니다. 'Command'는 무시됩니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 미리 정의된 매크로를 정의 또는 정의 해제하려고 합니다.

1. **정의된**전처리기 연산자를 정의 또는 정의 해제하려고 합니다.

다음 샘플에서는 C4117을 생성합니다.

```cpp
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```