---
title: 컴파일러 오류 C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 8145e0cdd97022ebdcc1a7ce38c8860a005945b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182446"
---
# <a name="compiler-error-c3446"></a>컴파일러 오류 C3446

>'*클래스*': 값 클래스의 멤버에 대 한 기본 멤버 이니셜라이저가 허용 되지 않습니다

Visual Studio 2015 이하에서는 컴파일러가 값 클래스 멤버에 대한 기본 멤버 이니셜라이저를 허용하지만 무시했습니다. 값 클래스의 기본 초기화는 항상 멤버를 0으로 초기화하고 기본 생성자는 허용되지 않습니다. Visual Studio 2017에서는 기본 멤버 이니셜라이저가 이 예제에 표시된 대로 컴파일러 오류를 발생시킵니다.

## <a name="example"></a>예제

다음 샘플에서는 Visual Studio 2017 이상 C3446 오류가 생성 됩니다.

```cpp
// C3446.cpp
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer
                  // is not allowed for a member of a value class
       int j {0}; // C3446
};
```

오류를 수정 하려면 이니셜라이저를 제거 합니다.

```cpp
// C3446b.cpp
value struct V
{
       int i;
       int j;
};
```

