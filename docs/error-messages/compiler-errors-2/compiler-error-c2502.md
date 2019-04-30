---
title: 컴파일러 오류 C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: e23ccae55c40c9652f5a3e1f55c834a968bca784
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165595"
---
# <a name="compiler-error-c2502"></a>컴파일러 오류 C2502

'identifier': 기본 클래스의 액세스 한정자가 너무 많습니다

기본 클래스에 둘 이상의 액세스 한정자입니다. 하나의 액세스 한정자 (`public`하십시오 `private`, 또는 `protected`) 허용 됩니다.

다음 샘플에서는 C2502를 생성합니다.

```
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```