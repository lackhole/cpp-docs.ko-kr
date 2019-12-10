---
title: 컴파일러 오류 C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: 6a51901477958056356a96d71adde4241d60a2ac
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750587"
---
# <a name="compiler-error-c2825"></a>컴파일러 오류 C2825

var: 뒤에 ':: '이 올 때 클래스 또는 네임 스페이스 여야 합니다.

정규화 된 이름을 형성 하지 못했습니다.

예를 들어, 함수 이름이::로 시작 하는 함수 선언이 코드에 포함 되어 있지 않은지 확인 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2825를 생성 합니다.

```cpp
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```
