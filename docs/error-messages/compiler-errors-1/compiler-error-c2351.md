---
title: 컴파일러 오류 C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: 6839d0c44efa10ba9507389fea35964fa748d646
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759973"
---
# <a name="compiler-error-c2351"></a>컴파일러 오류 C2351

사용 C++ 되지 않는 생성자 초기화 구문

생성자에 대 한 새 스타일 초기화 목록에서 유일한 기본 클래스 이더라도 각 직접 기본 클래스의 이름을 명시적으로 지정할 수 있습니다.

다음 샘플에서는 C2351를 생성 합니다.

```cpp
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```
