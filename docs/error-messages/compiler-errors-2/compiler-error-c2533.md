---
title: 컴파일러 오류 C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 00cb13d1999b00dfcaa5a2bc7bfb3b8eb16af5f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386982"
---
# <a name="compiler-error-c2533"></a>컴파일러 오류 C2533

'identifier': 생성자에서 반환 형식을 사용할 수 없습니다.

생성자는 반환 형식을 가질 수 없으며, `void` 반환 형식도 가질 수 없습니다.

이 오류의 일반적인 출처는 클래스 정의의 끝과 첫 번째 생성자 구현 사이에 누락된 세미콜론입니다. 컴파일러는 생성자 함수에 대한 반환 형식의 정의로 클래스를 인식하고 C2533을 생성합니다.

다음 샘플에서는 C2533을 생성하고 해결 방법을 보여 줍니다.

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```