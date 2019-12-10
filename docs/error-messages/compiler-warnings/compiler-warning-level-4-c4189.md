---
title: 컴파일러 경고(수준 4) C4189
ms.date: 11/04/2016
f1_keywords:
- C4189
helpviewer_keywords:
- C4189
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
ms.openlocfilehash: d403373fe200f10cb2f2c210b8cd8f58b7429198
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991501"
---
# <a name="compiler-warning-level-4-c4189"></a>컴파일러 경고(수준 4) C4189

'identifier': 지역 변수가 초기화되었으나 참조되지 않았습니다.

변수가 선언 및 초기화되었지만 사용되지 않습니다.

다음 샘플에서는 C4189를 생성합니다.

```cpp
// C4189.cpp
// compile with: /W4
int main() {
   int a = 1;   // C4189, remove declaration to resolve
}
```
