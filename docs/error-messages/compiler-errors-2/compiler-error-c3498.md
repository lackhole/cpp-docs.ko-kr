---
title: 컴파일러 오류 C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: 771e8c72ab4386bb45a11983318f412e784f5bc9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738104"
---
# <a name="compiler-error-c3498"></a>컴파일러 오류 C3498

' var ': 관리 되는 또는 WinRTtype을 포함 하는 변수를 캡처할 수 없습니다.

람다에 관리되는 형식 또는 Windows 런타임 형식이 있는 변수를 캡처할 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 관리되는 또는 Windows 런타임 변수를 람다 식의 매개 변수 목록에 전달합니다.

## <a name="example"></a>예제

다음 예제에서는 관리되는 형식이 있는 변수가 람다 식의 캡처 목록에 나타나므로 C3498을 생성합니다.

```cpp
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

## <a name="example"></a>예제

다음 예제에서는 관리되는 변수`s`를 람다 식의 매개 변수 목록에 전달하여 C3498을 해결합니다.

```cpp
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>참조

[람다 식](../../cpp/lambda-expressions-in-cpp.md)
