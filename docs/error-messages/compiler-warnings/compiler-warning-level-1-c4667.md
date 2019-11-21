---
title: 컴파일러 경고 (수준 1) C4667
ms.date: 11/04/2016
f1_keywords:
- C4667
helpviewer_keywords:
- C4667
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
ms.openlocfilehash: 9ae0d5cdcc1f6cca25f55cd1d7c03cc345c39e5e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051402"
---
# <a name="compiler-warning-level-1-c4667"></a>컴파일러 경고 (수준 1) C4667

' function ': 강제 인스턴스화와 일치 하도록 정의 된 함수 템플릿이 없습니다.

선언 되지 않은 함수 템플릿을 인스턴스화할 수 없습니다.

다음 샘플에서는 C4667을 발생 시킵니다.

```cpp
// C4667a.cpp
// compile with: /LD /W1
template
void max(const int &, const int &); // C4667 expected
```

이 경고를 방지 하려면 먼저 함수 템플릿을 선언 합니다.

```cpp
// C4667b.cpp
// compile with: /LD
// Declare the function template
template<typename T>
const T &max(const T &a, const T &b) {
   return (a > b) ? a : b;
}
// Then forcibly instantiate it with a desired type ... i.e. 'int'
//
template
const int &max(const int &, const int &);
```