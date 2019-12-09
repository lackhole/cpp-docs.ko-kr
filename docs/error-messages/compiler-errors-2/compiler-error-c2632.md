---
title: 컴파일러 오류 C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: f69d43bf50f5f13957e49d1e9ffa798a3db5a7b3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754695"
---
# <a name="compiler-error-c2632"></a>컴파일러 오류 C2632

' type1 ' 뒤에 ' type2 '가 올 수 없습니다.

두 형식 지정자 사이에 누락 된 코드가 있는 경우이 오류가 발생할 수 있습니다.

다음 샘플에서는 C2632를 생성 합니다.

```cpp
// C2632.cpp
int float i;   // C2632
```

이 오류는 Visual Studio .NET 2003에 대해 수행 된 컴파일러 규칙 작업의 결과로도 생성 될 수 있습니다. 이제 `bool` 적절 한 형식입니다. 이전 버전에서 `bool`는 typedef 이며 해당 이름을 사용 하 여 식별자를 만들 수 있습니다.

다음 샘플에서는 C2632를 생성 합니다.

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Visual Studio .NET 2003 및 visual Studio .NET 버전 C++의 visual studio에서 코드를 모두 사용할 수 있도록이 오류를 해결 하려면 식별자의 이름을 바꿉니다.
