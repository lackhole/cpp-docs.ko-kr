---
title: 컴파일러 오류 C2045
ms.date: 11/04/2016
f1_keywords:
- C2045
helpviewer_keywords:
- C2045
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
ms.openlocfilehash: cf3644c49e424315fb406fa9548fcf6ce1bfcbc7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740379"
---
# <a name="compiler-error-c2045"></a>컴파일러 오류 C2045

'identifier': 레이블이 재정의되었습니다.

레이블이 같은 함수의 여러 문 앞에 나타납니다.

다음 샘플에서는 C2045를 생성합니다.

```cpp
// C2045.cpp
int main() {
   label: {
   }
   goto label;
   label: {}   // C2045
}
```
