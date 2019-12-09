---
title: 컴파일러 오류 C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: f3e728033a3230d628242aab341377be2f6670ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760259"
---
# <a name="compiler-error-c2687"></a>컴파일러 오류 C2687

' type ': 예외 선언은 ' void ' 일 수 없으며 불완전 한 형식 또는 불완전 한 형식에 대 한 포인터 또는 참조를 나타낼 수 없습니다.

형식이 예외 선언의 일부가 되려면 void가 아닌 정의 되어야 합니다.

다음 샘플에서는 C2687를 생성 합니다.

```cpp
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

가능한 해결 방법:

```cpp
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```
