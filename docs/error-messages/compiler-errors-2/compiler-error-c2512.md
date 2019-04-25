---
title: 컴파일러 오류 C2512
ms.date: 02/09/2018
f1_keywords:
- C2512
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
ms.openlocfilehash: 16a1da0e882cd178c9e01737480d74eb23c7c38c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164828"
---
# <a name="compiler-error-c2512"></a>컴파일러 오류 C2512

> '*식별자*': 해당 하는 기본 생성자를 사용할 수 없음

A *기본 생성자*를 인수 없이 필요한 생성자는 지정 된 클래스, 구조체 또는 공용 구조체 사용할 수 없습니다. 컴파일러는 없는 사용자 정의 생성자가 제공 하는 경우에 기본 생성자를 제공 합니다.

Void가 아닌 매개 변수를 사용 하는 생성자를 제공 하는 경우 클래스 (예를 들어, 배열 요소)로 매개 변수 없이 만들 수 있도록 하려면 기본 생성자도 제공 해야 합니다. 기본 생성자는 모든 매개 변수에 기본값을 사용하는 생성자일 수 있습니다.

## <a name="example"></a>예제

C2512 오류의 일반적인 원인은 인수를 사용 하는 클래스 또는 구조체 생성자를 정의 하는 경우 이며 다음 인수 없이 구조체 또는 클래스의 인스턴스를 선언 하려고 합니다. 예를 들어 `struct B` 필요로 하는 생성자를 선언 아래는 `char *` 인수를 제외 하 고 인수를 사용 하지. `main`B의 인스턴스를 선언 되지만 인수가 없습니다. 2.에 대 한 기본 생성자를 찾을 수 없어 컴파일러에서는 C2512를 생성

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

와 같은 구조체 또는 클래스에 대해 기본 생성자를 정의 하 여이 문제를 해결할 수 있습니다 `B() {}`, 또는 모든 인수가 기본값으로 있는 같은 생성자 `B (char * = nullptr) {}`합니다.
