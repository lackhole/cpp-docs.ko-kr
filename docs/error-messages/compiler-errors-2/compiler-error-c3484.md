---
title: 컴파일러 오류 C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: c9895a3e5a8ae7e941fccde2da85fedfb3d2c6dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743122"
---
# <a name="compiler-error-c3484"></a>컴파일러 오류 C3484

반환 형식 앞에 '->'가 필요합니다.

람다 식의 반환 형식 앞에 `->` 를 제공해야 합니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 반환 형식 앞에 `->` 를 제공합니다.

## <a name="example"></a>예제

다음 예제에서는 C3484를 생성합니다.

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>예제

다음 예제에서는 람다 식의 반환 형식 앞에 `->` 를 제공하여 C3484를 해결합니다.

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>참조

[람다 식](../../cpp/lambda-expressions-in-cpp.md)
