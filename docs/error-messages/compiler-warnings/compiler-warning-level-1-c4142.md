---
title: 컴파일러 경고 (수준 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: 762f52c9f051a660cce68d424e02fc45422376e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302282"
---
# <a name="compiler-warning-level-1-c4142"></a>컴파일러 경고 (수준 1) C4142

형식 재정의가

형식이 생성된 된 코드에 영향을 주지 않는 방식으로 재정의 되었습니다.

다음과 같은 가능한 원인을 확인하여 수정하세요.

- 파생된 클래스의 멤버 함수에는 기본 클래스의 해당 멤버 함수에서 다른 반환 형식이 있습니다.

- 사용 하 여 정의 된 형식은 `typedef` 명령은 서로 다른 구문을 사용 하 여 재정의 됩니다.

다음 샘플에서는 C4142 오류가 생성 됩니다.

```
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```