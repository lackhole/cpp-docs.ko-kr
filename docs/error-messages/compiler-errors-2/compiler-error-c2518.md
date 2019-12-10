---
title: 컴파일러 오류 C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: 894167fce43147b98af6603cba3102e5714b850e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746489"
---
# <a name="compiler-error-c2518"></a>컴파일러 오류 C2518

기본 클래스 목록에 ' keyword ' 키워드가 잘못 되었습니다. 무시

`class` 및 `struct` 키워드는 기본 클래스 목록에 표시 되지 않아야 합니다.

다음 샘플에서는 C2518를 생성 합니다.

```cpp
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```
