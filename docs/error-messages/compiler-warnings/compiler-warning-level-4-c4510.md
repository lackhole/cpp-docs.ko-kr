---
title: 컴파일러 경고(수준 4) C4510
ms.date: 11/04/2016
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: 80183e9f7ef17cbc37592f36eb8db1df2be94827
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221092"
---
# <a name="compiler-warning-level-4-c4510"></a>컴파일러 경고(수준 4) C4510

'class': 기본 생성자를 생성할 수 없습니다

컴파일러는 지정된 된 클래스에 대 한 기본 생성자를 생성할 수 없습니다 및 생성 된 사용자 정의 생성자가 없습니다. 이 형식의 개체를 만들 수 없습니다.

컴파일러가 기본 생성자를 생성 하지 못하도록 하는 몇 가지 경우가 포함:

- Const 데이터 멤버입니다.

- 데이터 멤버는 참조입니다.

이러한 멤버를 초기화 하는 클래스에 대 한 사용자 정의 기본 생성자를 생성 해야 합니다.

다음 샘플에서는 C4510 오류가 생성 됩니다.

```
// C4510.cpp
// compile with: /W4
struct A {
   const int i;
   int &j;
   A& operator=( const A& ); // C4510 expected
   // uncomment the following line to resolve this C4510
   // A(int ii, int &jj) : i(ii), j(jj) {}
};   // C4510

int main() {
}
```