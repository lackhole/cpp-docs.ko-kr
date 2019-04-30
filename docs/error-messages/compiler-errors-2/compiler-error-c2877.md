---
title: 컴파일러 오류 C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: 093efbf0c329967983c1808ee46011425745515f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390635"
---
# <a name="compiler-error-c2877"></a>컴파일러 오류 C2877

'symbol'를 'class'에서 액세스할 수 없는 경우

기본 클래스에서 파생 된 모든 멤버는 파생된 클래스에서 액세스할 수 있어야 합니다.

다음 샘플에서는 C2877 오류가 생성 됩니다.

```
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```