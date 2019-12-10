---
title: 컴파일러 오류 C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: f5a62b1c12b94735d0383697bf7a92d12d64b21f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757802"
---
# <a name="compiler-error-c2243"></a>컴파일러 오류 C2243

'type1'에서 'type2'로 'conversion type' 변환이 있지만 액세스할 수 없습니다.

액세스 보호(`protected` 또는 `private`)로 인해 파생 클래스에 대한 포인터에서 기본 클래스에 대한 포인터로의 변환이 차단되었습니다.

다음 샘플에서는 C2243 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

`protected` 또는 `private` 액세스가 있는 기본 클래스는 파생 클래스의 클라이언트에 액세스할 수 없습니다. 이 수준의 액세스 제어는 기본 클래스가 클라이언트에 표시되지 않아야 하는 구현 정보임을 나타내는 데 사용됩니다. 파생 클래스의 클라이언트가 파생 클래스 포인터에서 기본 클래스 포인터로의 암시적 변환에 액세스하게 하려면 공용 파생을 사용합니다.
