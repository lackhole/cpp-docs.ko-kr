---
title: 컴파일러 경고 (수준 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 40c6724daf17c1c0b546bb7bc64bb704f732e8d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386553"
---
# <a name="compiler-warning-level-1-c4010"></a>컴파일러 경고 (수준 1) C4010

줄으로 된 주석 줄 연속 문자를 포함합니다.

도입 된 한 줄으로 된 주석, / / 백슬래시를 포함 (\\) 줄 연속 문자는 역할을 합니다. 컴파일러는 연속으로 다음 줄을 고려 하 고 주석으로 처리 합니다.

일부 구문 지향 편집기 주석으로 연속 문자를 다음 줄을 나타내지 않습니다. 이 경고를 발생 시키는 줄에 대 한 구문 색을 무시 합니다.

다음 샘플에서는 C4010 오류가 생성 됩니다.

```
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```