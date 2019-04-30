---
title: 컴파일러 오류 C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: 18d8f7130c34f5e1e33bc7aa9b9463f50c243045
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386943"
---
# <a name="compiler-error-c2589"></a>컴파일러 오류 C2589

'identifier': 오른쪽에 잘못 된 토큰 ': '

클래스, 구조체 또는 공용 구조체 이름은 범위 결정 연산자 (이중 콜론)의 왼쪽에 있으면 오른쪽의 토큰 클래스, 구조체 또는 공용 구조체 멤버 여야 합니다. 그렇지 않은 경우 모든 전역 식별자 오른쪽에 나타날 수 있습니다.

범위 결정 연산자를 오버 로드할 수 없습니다.

다음 샘플에서는 C2589 오류가 생성 됩니다.

```
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```