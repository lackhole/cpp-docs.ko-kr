---
title: 컴파일러 오류 C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 63f9594eb9ee8a251faafe7323418b343c03063c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165231"
---
# <a name="compiler-error-c2507"></a>컴파일러 오류 C2507

'identifier': 기본 클래스에 가상 한정자가 너무 많습니다

으로 선언 된 클래스 또는 구조체 `virtual` 두 번 이상. 하나의 `virtual` 한정자 기본 클래스 목록의 각 클래스에 대해 표시할 수 있습니다.

다음 샘플에서는 C2507 오류가 생성 됩니다.

```
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```