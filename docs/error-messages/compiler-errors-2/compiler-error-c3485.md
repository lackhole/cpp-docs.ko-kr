---
title: 컴파일러 오류 C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 2fcaecd6be35e2ae6822133930b48b6bbf02aafe
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027586"
---
# <a name="compiler-error-c3485"></a>컴파일러 오류 C3485

람다 정의에 cv 한정자를 사용할 수 없습니다.

`const` 또는 `volatile` 한정자를 람다 식 정의의 일부로 사용할 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 람다 식 정의에서 `const` 또는 `volatile` 한정자를 제거합니다.

## <a name="example"></a>예제

다음 예제에서는 `const` 한정자를 람다 식 정의의 일부로 사용하므로 C3485가 생성됩니다.

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>참고자료

[람다 식](../../cpp/lambda-expressions-in-cpp.md)