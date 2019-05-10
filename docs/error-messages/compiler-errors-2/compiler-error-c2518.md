---
title: 컴파일러 오류 C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: d0a1f7bdc493a16b38dc2348097cc6cbea7ed898
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282289"
---
# <a name="compiler-error-c2518"></a>컴파일러 오류 C2518

기본 클래스 목록에 잘못 된 ' keyword' 키워드 무시

키워드 `class` 고 `struct` 기본 클래스 목록에 나타나지 않아야 합니다.

다음 샘플에서는 C2518 오류가 생성 됩니다.

```
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```