---
title: 컴파일러 경고(수준 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: fe96ff50f4081e3c9dbe3c7eb68da156a69c96ab
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776368"
---
# <a name="compiler-warning-level-4-c4481"></a>컴파일러 경고(수준 4) C4481

비표준 확장이 사용 됨: 재정의 지정자는 'keyword'

키워드는 c + + 표준, /clr에서 작동 하는 재정의 지정자 중 하나가 예를 들어, 포함에서 되지 않은 사용 되었습니다.  자세한 내용은 다음 항목을 참조하세요.

- [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Override 지정자](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>예제

다음 샘플에서는 C4481 오류가 발생 합니다.

```
// C4481.cpp
// compile with: /W4 /c
class B {
   virtual void f(unsigned);
};

class C : B {
   void f(unsigned) override;   // C4481
   void f2(unsigned);
};
```