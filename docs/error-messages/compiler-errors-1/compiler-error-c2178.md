---
title: 컴파일러 오류 C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: cd153bb5b331872bfe35b046d41612998bd0eff7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386007"
---
# <a name="compiler-error-c2178"></a>컴파일러 오류 C2178

'*식별자*'로 선언할 수 없습니다'*지정자*' 지정자

`mutable` 선언에서 지정자를 사용한 있지만 지정자를이 컨텍스트에서 허용 되지 않습니다.

합니다 `mutable` 지정자 클래스 데이터 멤버의 이름에만 적용 될 수 있으며 이름 선언에 적용할 수 없습니다 `const` 또는 `static`, 멤버를 참조 하는 적용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2178 발생할 수 있습니다 하는 방법 및 해결 하는 방법을 보여 줍니다.

```
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```
