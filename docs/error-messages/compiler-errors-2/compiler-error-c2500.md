---
title: 컴파일러 오류 C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: 152546fce8f3ee63f8b95595bff052f18cd4ebda
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746970"
---
# <a name="compiler-error-c2500"></a>컴파일러 오류 C2500

' identifier1 ': ' identifier2 '은 (는) 이미 직접 기본 클래스입니다.

클래스 또는 구조체가 기본 클래스 목록에 두 번 이상 나타납니다.

직접 기본은 기본 목록에서 언급 한 것입니다. 간접 기본 클래스는 기본 목록에 있는 클래스 중 하나의 기본 클래스입니다.

클래스를 직접 기본 클래스로 두 번 이상 지정할 수 없습니다. 클래스를 간접 기본 클래스로 두 번 이상 사용할 수 있습니다.

다음 샘플에서는 C2500를 생성 합니다.

```cpp
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```
