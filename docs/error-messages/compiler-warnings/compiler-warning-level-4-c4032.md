---
title: 컴파일러 경고 (수준 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 52e80340a5157e9350b6d4bbf3bcabea0487e089
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541254"
---
# <a name="compiler-warning-level-4-c4032"></a>컴파일러 경고 (수준 4) C4032

' number ' 형식 매개 변수의 형식이 서로 다릅니다.

매개 변수 형식은 기본 프로 모션을 통해 이전 선언의 형식과 호환 되지 않습니다.

이 오류는 ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md))의 오류 이며 Microsoft 확장 (/ze)에서 경고가 발생 합니다.

## <a name="example"></a>예제

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```