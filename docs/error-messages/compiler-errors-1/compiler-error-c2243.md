---
title: 컴파일러 오류 C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: ded5a3d459e4b5d1412998aadbaa385864f505a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388871"
---
# <a name="compiler-error-c2243"></a>컴파일러 오류 C2243

'type1'에서 'type2'로 'conversion type' 변환이 있지만 액세스할 수 없습니다.

액세스 보호(`protected` 또는 `private`)로 인해 파생 클래스에 대한 포인터에서 기본 클래스에 대한 포인터로의 변환이 차단되었습니다.

다음 샘플에서는 C2243 오류가 발생하는 경우를 보여 줍니다.

```
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