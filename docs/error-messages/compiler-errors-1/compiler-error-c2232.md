---
title: 컴파일러 오류 C2232
ms.date: 11/04/2016
f1_keywords:
- C2232
helpviewer_keywords:
- C2232
ms.assetid: 76f302b7-30a7-4a81-9a39-b4edde33b54c
ms.openlocfilehash: f1478c2d06ab535a532b1be45c2db69050afe7b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376642"
---
# <a name="compiler-error-c2232"></a>컴파일러 오류 C2232

'->': 왼쪽된 피연산자 형식이 ' 클래스 키 '를 사용 하 여 '.'

`->` 연산자의 왼쪽에 있는 피연산자가 포인터가 아닙니다. 마침표 (.) 연산자를 사용 하 여 클래스, 구조체 또는 공용 구조체에 대 한 합니다.

다음 샘플에서는 C2232를 생성합니다.

```
// C2232.c
struct X {
    int member;
} x, *px;
int main() {
    x->member = 0;   // C2232, x is not a pointer

    px->member = 0;
    x.member = 0;
}
```