---
title: 컴파일러 경고 (수준 1) C4003
ms.date: 11/04/2016
f1_keywords:
- C4003
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
ms.openlocfilehash: 7b1b87c643111f2b12124e348be8fb823e113937
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187315"
---
# <a name="compiler-warning-level-1-c4003"></a>컴파일러 경고 (수준 1) C4003

'identifier' 매크로의 실제 매개 변수가 부족합니다.

매크로 정의의 정식 매개 변수 수가 매크로의 실제 매개 변수 수를 초과합니다. 누락 된 매개 변수가 빈 텍스트로 대체 하는 매크로 확장 합니다.

다음 샘플에서는 C4003 오류가 생성 됩니다.

```
// C4003.cpp
// compile with: /WX
#define test(a,b) (a+b)

int main()
{
   int a = 1;
   int b = 2;
   a = test(b);   // C4003
   // try..
   a = test(a,b);
}
```