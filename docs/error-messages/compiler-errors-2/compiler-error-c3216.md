---
title: 컴파일러 오류 C3216
ms.date: 11/04/2016
f1_keywords:
- C3216
helpviewer_keywords:
- C3216
ms.assetid: bbab1efe-8779-4489-8bb0-b11e45f5cbe5
ms.openlocfilehash: 6b4f51dc0e27381ef64fc6cd1e4e279736a725aa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751263"
---
# <a name="compiler-error-c3216"></a>컴파일러 오류 C3216

제약 조건은 'type'이 아니라 제네릭 매개 변수여야 합니다.

제약 조건 형식이 잘못되었습니다.

다음 샘플에서는 C3216을 생성합니다.

```cpp
// C3216.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where F : A   // C3216
// Try the following line instead:
// where T : A    // C3216
ref class C {};
```

다음 예제에서는 가능한 해결 방법을 설명합니다.

```cpp
// C3216b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```
