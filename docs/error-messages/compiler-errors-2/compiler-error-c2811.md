---
title: 컴파일러 오류 C2811
ms.date: 11/04/2016
f1_keywords:
- C2811
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
ms.openlocfilehash: 8dfc462cc0eedfff1661ae38f79bbb79c5c1a8fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281757"
---
# <a name="compiler-error-c2811"></a>컴파일러 오류 C2811

'type1': ref 'type2'에서 상속할 수 없습니다. 클래스는 ref 클래스 또는 인터페이스 클래스 에서만 상속할 수

관리 되지 않는 클래스를 관리 되는 클래스에 대 한 기본 클래스로 사용 하려고 했습니다.

다음 샘플에서는 C2811 오류가 생성 됩니다.

```
// C2811.cpp
// compile with: /clr /c
struct S{};
ref struct T {};
ref class C : public S {};   // C2811
ref class D : public T {};   // OK
```