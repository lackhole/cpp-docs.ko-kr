---
title: 컴파일러 오류 C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d20b8dde9f4134273adcba0f947f685f7ce7d213
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408526"
---
# <a name="compiler-error-c2803"></a>컴파일러 오류 C2803

'operator o'는 클래스 형식의 정식 매개 변수가 하나 이상 있어야 합니다.

오버 로드 된 연산자에는 클래스 형식 매개 변수가 없습니다.

또는 값을 쓸 수 참조 (포인터 되지만 참조는 사용 하지 않음)에서 하나 이상의 매개 변수를 전달 해야 "는 < b" (한와 b는 클래스 A 형식입니다).

두 매개 변수는 포인터의 포인터 주소 순수 하 게 비교 됩니다 및 사용자 정의 변환을 사용 하지 않습니다.

다음 샘플에서는 C2803 오류가 생성 됩니다.

```
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```