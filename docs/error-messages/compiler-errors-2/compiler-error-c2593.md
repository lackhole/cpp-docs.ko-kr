---
title: 컴파일러 오류 C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: c358553a36104b5c389076f5a5ce02f94f85e85a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386917"
---
# <a name="compiler-error-c2593"></a>컴파일러 오류 C2593

'연산자 identifier' 모호합니다.

둘 이상의 가능한 연산자를 오버 로드 된 연산자에 대해 정의 됩니다.

하나 이상의 실제 매개 변수에서 명시적 캐스트를 사용 하는 경우이 오류를 해결할 수 있습니다.

다음 샘플에서는 C2593을 생성합니다.

```
// C2593.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};
void operator+( X, X );
void operator+( A, B );
D d;

int main() {
   d +  d;         // C2593, D has an A, B, and X
   (X)d + (X)d;    // OK, uses operator+( X, X )
}
```

이 오류를 사용 하 여 부동 소수점 변수를 직렬화 하 여 발생할 수 있습니다는 `CArchive` 개체입니다. 컴파일러 하 게 식별 하는 `<<` 모호 하다는 연산자입니다. 만 기본 C++ 유형에 `CArchive` serialize 할 수는 고정 크기 형식 `BYTE`, `WORD`, `DWORD`, 및 `LONG`. 모든 정수 형식 serialization에 대 한 이러한 형식 중 하나로 캐스팅 되어야 합니다. 부동 소수점 형식을 사용 하 여 보관 해야 합니다 `CArchive::Write()` 멤버 함수입니다.

다음 예제에서는 부동 소수점 변수에 보관 하는 방법을 보여 줍니다 (`f`)에서 보관 `ar`:

```
ar.Write(&f, sizeof( float ));
```