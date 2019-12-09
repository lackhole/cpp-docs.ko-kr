---
title: 컴파일러 오류 C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: 4f09c7e250b4c2b02ba2db582f92d54336bed673
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761792"
---
# <a name="compiler-error-c3168"></a>컴파일러 오류 C3168

' type ': 열거형의 내부 형식이 잘못 되었습니다.

`enum` 형식에 대해 지정한 기본 형식이 잘못 되었습니다. 내부 형식은 정수 C++ 형식 또는 해당 CLR 형식 이어야 합니다.

다음 샘플에서는 C3168를 생성 합니다.

```cpp
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
