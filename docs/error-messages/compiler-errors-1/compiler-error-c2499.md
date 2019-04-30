---
title: 컴파일러 오류 C2499
ms.date: 11/04/2016
f1_keywords:
- C2499
helpviewer_keywords:
- C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
ms.openlocfilehash: 645dd3923e65240de17803a8831a0223ff0e1656
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360556"
---
# <a name="compiler-error-c2499"></a>컴파일러 오류 C2499

'class': 클래스는 자체 기본 클래스일 수 없습니다

기본 클래스로 정의 하는 클래스를 지정 하려고 했습니다.

다음 샘플에서는 C2499 오류가 생성 됩니다.

```
// C2499.cpp
// compile with: /c
class CMyClass : public CMyClass {};   // C2499
class CMyClass{};   // OK
```