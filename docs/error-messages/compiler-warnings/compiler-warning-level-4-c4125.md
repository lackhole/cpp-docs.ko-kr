---
title: 컴파일러 경고(수준 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 3b82bfd1a1acff07a0fd47bbd2abfb08178a74c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401360"
---
# <a name="compiler-warning-level-4-c4125"></a>컴파일러 경고(수준 4) C4125

10진수가 8진수 이스케이프 시퀀스를 마칩니다.

컴파일러가 10진수 없는 8진수를 계산하고 10진수를 문자로 가정합니다.

## <a name="example"></a>예제

```
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

숫자 9가 문자로 사용된 경우 예제를 다음과 같이 수정합니다.

```
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```