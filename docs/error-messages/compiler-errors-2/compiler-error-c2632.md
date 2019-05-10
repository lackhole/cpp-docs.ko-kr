---
title: 컴파일러 오류 C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b92d44bcfd04d4de7b39c5bdab5ee146d9b6693b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257636"
---
# <a name="compiler-error-c2632"></a>컴파일러 오류 C2632

'type1' 'type2' 뒤에 올바르지 않습니다.

이 오류는 두 가지 형식 지정자 사이 코드가 누락 된 경우 발생할 수 있습니다.

다음 샘플에서는 C2632 오류가 생성 됩니다.

```
// C2632.cpp
int float i;   // C2632
```

이 오류 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수도 있습니다. `bool` 이제 적절 한 형식이입니다. 이전 버전에서는 `bool` typedef에서 되었으며 해당 이름의 식별자를 만들 수 있습니다.

다음 샘플에서는 C2632 오류가 생성 됩니다.

```
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

코드의 시각적 개체의 Visual Studio.NET 2003와 VISUAL Studio 버전에서 유효한이 오류를 해결 하려면 C++, 식별자 이름을 바꿉니다.