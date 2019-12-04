---
title: 컴파일러 오류 C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 2b57f3346427ff548d11fe776e909eca99433a81
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749037"
---
# <a name="compiler-error-c3908"></a>컴파일러 오류 C3908

' 구문 ' 보다 액세스 수준이 덜 제한적입니다.

속성 접근자 메서드 (get 또는 set)는 속성 자체에 지정 된 액세스 보다 덜 제한적으로 액세스할 수 없습니다.  마찬가지로 이벤트 접근자 메서드의 경우입니다.

자세한 내용은 [속성](../../extensions/property-cpp-component-extensions.md) 및 [이벤트](../../extensions/event-cpp-component-extensions.md)를 참조 하세요.

다음 샘플에서는 C3908를 생성 합니다.

```cpp
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```
