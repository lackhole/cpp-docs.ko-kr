---
title: 컴파일러 오류 C3215
ms.date: 11/04/2016
f1_keywords:
- C3215
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
ms.openlocfilehash: 59d9eb0c28269e95b906042126cc3a9f25bba635
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751913"
---
# <a name="compiler-error-c3215"></a>컴파일러 오류 C3215

'type1': 제네릭 형식 매개 변수가 이미 'type2'의 제약을 받습니다.

제약 조건을 두 번 이상 지정했습니다.

제네릭에 대한 자세한 내용은 [Generics](../../extensions/generics-cpp-component-extensions.md)을 참조하세요.

다음 샘플에서는 C3215를 생성합니다.

```cpp
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

가능한 해결 방법:

```cpp
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```
