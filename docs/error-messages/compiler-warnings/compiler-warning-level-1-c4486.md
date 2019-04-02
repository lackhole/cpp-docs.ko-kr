---
title: 컴파일러 경고(수준 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: 402d5eefde6c2dfd5693e53c27edb00d1ac2e56c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58780212"
---
# <a name="compiler-warning-level-1-c4486"></a>컴파일러 경고(수준 1) C4486

'function': ref 클래스 또는 값 클래스의 전용 가상 메서드를 'sealed'으로 표시 되어야 합니다

관리 되는 클래스 또는 구조체의 전용 가상 멤버 함수는 액세스 또는 재정의가 가능 없습니다, 하므로 표시 되어야 합니다 [봉인](../../extensions/sealed-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4486 오류가 발생 합니다.

```
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

## <a name="example"></a>예제

다음 샘플에서는 개인 sealed로 표시 된 가상 함수는 한 가지 가능한 용도 보여 줍니다.

```
// C4486_b.cpp
// compile with: /clr /c
ref class B {};

ref class D : B {};

interface class I {
   B^ mf();
};

ref class E : I {
private:
   virtual B^ g() sealed = I::mf {
      return gcnew B;
   }

public:
   virtual D^ mf() {
      return gcnew D;
   }
};
```