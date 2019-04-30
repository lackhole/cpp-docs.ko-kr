---
title: 컴파일러 경고 (수준 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: b2406357baf70e45566f2d2f25839d151bac4186
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352951"
---
# <a name="compiler-warning-level-1-c4144"></a>컴파일러 경고 (수준 1) C4144

'expression': 관계식을 switch 식

지정한 관계식의 제어 식으로 사용한를 [전환](../../cpp/switch-statement-cpp.md) 문입니다. 관련 된 case 문에 부울 값이 제공 됩니다. 다음 샘플에서는 C4144 오류가 생성 됩니다.

```
// C4144.cpp
// compile with: /W1
int main()
{
   int i = 0;
   switch(!i) {   // C4144, remove the ! to resolve
      case 1:
         break;
      default:
         break;
   }
}
```