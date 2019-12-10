---
title: 컴파일러 오류 C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d39f737ba02f3fa9c9d5f61594ddf730db6739a5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760662"
---
# <a name="compiler-error-c2803"></a>컴파일러 오류 C2803

' operator operator '에는 클래스 형식의 정식 매개 변수를 하나 이상 포함 해야 합니다.

오버 로드 된 연산자에 클래스 형식의 매개 변수가 없습니다.

하나 이상의 매개 변수를 참조로 전달 하거나 (참조는 사용 하지 않음), 값을 사용 하 여 "a < b"를 작성할 수 있어야 합니다 (a 및 b는 클래스 A 형식).

두 매개 변수가 모두 포인터인 경우 포인터 주소를 순수 하 게 비교 하 고 사용자 정의 변환을 사용 하지 않습니다.

다음 샘플에서는 C2803를 생성 합니다.

```cpp
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```
