---
title: 컴파일러 오류 C3747
ms.date: 11/04/2016
f1_keywords:
- C3747
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
ms.openlocfilehash: 761bb44f5097d998fd885fdb1c5caacf90db3642
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761870"
---
# <a name="compiler-error-c3747"></a>컴파일러 오류 C3747

기본 형식 매개 변수가 없습니다. 매개 변수 매개 변수

기본값이 있는 제네릭 또는 템플릿 매개 변수는 매개 변수 목록에서 기본값이 없는 매개 변수에 따라 올 수 없습니다.

다음 샘플에서는 C3747를 생성 합니다.

```cpp
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

가능한 해결 방법:

```cpp
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```
