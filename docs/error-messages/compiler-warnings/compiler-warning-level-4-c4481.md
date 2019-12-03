---
title: 컴파일러 경고(수준 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: fb51d16cc15c244b31d65f7777de66c372bbde33
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683199"
---
# <a name="compiler-warning-level-4-c4481"></a>컴파일러 경고(수준 4) C4481

비표준 확장이 사용 됨: ' keyword ' 지정자를 재정의 합니다.

C++ 표준에 없는 키워드 (예:/clr에서 작동 하는 재정의 지정자 중 하나)가 사용 되었습니다.  자세한 내용은 다음 항목을 참조하세요.

- [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Override 지정자](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>예제

다음 샘플에서는 C4481를 생성 합니다.

```cpp
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