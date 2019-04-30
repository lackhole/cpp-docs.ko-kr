---
title: 컴파일러 오류 C2788
ms.date: 11/04/2016
f1_keywords:
- C2788
helpviewer_keywords:
- C2788
ms.assetid: 8688fc5c-e652-43b4-b407-9c488c76f2db
ms.openlocfilehash: 0025aa5211c2736860bdd30cad4315f63fba9337
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256895"
---
# <a name="compiler-error-c2788"></a>컴파일러 오류 C2788

'identifier':이 개체와 관련 된 둘 이상의 GUID

합니다 [__uuidof](../../cpp/uuidof-operator.md) 연산자 연결 된 GUID 또는 사용자 정의 형식의 개체를 사용 하 여 사용자 정의 형식을 사용 합니다. 이 오류는 인수는 여러 Guid 사용 하 여 개체인 경우에 발생 합니다.

다음 샘플에서는 C2788 오류가 생성 됩니다.

```
// C2788.cpp
#include <windows.h>
struct __declspec(uuid("00000001-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000002-0000-0000-0000-000000000000}")) B {};
template <class T, class U> class MyClass {};

typedef MyClass<A,B> MyBadClass;
typedef MyClass<A,A> MyGoodClass;

int main() {
   __uuidof(MyBadClass);    // C2788
   // try the following line instead
   __uuidof(MyGoodClass);
}
```