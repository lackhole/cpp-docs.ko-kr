---
title: 컴파일러 오류 C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: 5f44c94cbb3c945406835816d8fc6ed7c39480eb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742628"
---
# <a name="compiler-error-c3633"></a>컴파일러 오류 C3633

' member '를 관리 되는 ' type '의 멤버로 정의할 수 없습니다.

CLR 참조 클래스 데이터 멤버는 비 POD C++ 형식일 수 없습니다.  CLR 형식에서는 POD 네이티브 형식만 인스턴스화할 수 있습니다.  예를 들어 POD 형식에는 복사 생성자 또는 대입 연산자를 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3633를 생성 합니다.

```cpp
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
