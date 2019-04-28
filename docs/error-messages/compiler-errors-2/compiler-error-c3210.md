---
title: 컴파일러 오류 C3210
ms.date: 11/04/2016
f1_keywords:
- C3210
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
ms.openlocfilehash: 9e0ac1aded7eef40be0e923b3ac1ebc9ef00c7a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182537"
---
# <a name="compiler-error-c3210"></a>컴파일러 오류 C3210

'type': 액세스 선언은 기본 클래스 멤버에만 적용할 수 있습니다

A [선언을 사용 하 여](../../cpp/using-declaration.md) 잘못 지정 되었습니다.

## <a name="example"></a>예제

다음 샘플 C3210를 생성합니다.

```
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```