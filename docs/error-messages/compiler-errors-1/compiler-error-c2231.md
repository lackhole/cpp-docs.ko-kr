---
title: 컴파일러 오류 C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 0d6519bd12cdb5ee5a86fa4a6915b51b0dc59fc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383310"
---
# <a name="compiler-error-c2231"></a>컴파일러 오류 C2231

'.': 왼쪽 피연산자를 가리킵니다 ' 클래스 키 ', '->' 사용

멤버 선택 연산자 (.)의 왼쪽 피연산자는 클래스, 구조체 또는 공용 구조체 대신 포인터입니다.

다음 샘플에서는 C2231을 생성합니다.

```
// C2231.c
struct S {
   int member;
} s, *ps = &s;
int main() {
   ps.member = 0;   // C2231

   // OK
   ps->member = 0;   // crash
   s.member = 0;
}
```