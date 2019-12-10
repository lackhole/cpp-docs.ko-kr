---
title: 컴파일러 오류 C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 0eacb6ce6426674d23fc78596ead3730f46ae370
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743044"
---
# <a name="compiler-error-c3485"></a>컴파일러 오류 C3485

람다 정의에 cv 한정자를 사용할 수 없습니다.

`const` 또는 `volatile` 한정자를 람다 식 정의의 일부로 사용할 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 람다 식 정의에서 `const` 또는 `volatile` 한정자를 제거합니다.

## <a name="example"></a>예제

다음 예제에서는 `const` 한정자를 람다 식 정의의 일부로 사용하므로 C3485가 생성됩니다.

```cpp
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>참조

[람다 식](../../cpp/lambda-expressions-in-cpp.md)
