---
title: 컴파일러 오류 C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: b9542f1904c6797a77c88c88a37aff9348364268
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738182"
---
# <a name="compiler-error-c3496"></a>컴파일러 오류 C3496

'this'는 항상 값으로 캡처됩니다. '&'가 무시되었습니다.

참조에 의해 `this` 포인터를 캡처할 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 값으로 `this` 포인터를 캡처합니다.

## <a name="example"></a>예제

다음 예제에서는 `this` 포인터에 대한 참조가 람다 식의 캡처 목록에 나타나므로 C3496을 생성합니다.

```cpp
// C3496.cpp
// compile with: /c

class C
{
   void f()
   {
      [&this] {}(); // C3496
   }
};
```

## <a name="see-also"></a>참조

[람다 식](../../cpp/lambda-expressions-in-cpp.md)
