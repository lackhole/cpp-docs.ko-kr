---
title: 컴파일러 경고(수준 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: f194f0efc8012bf027e4785c2f398a0a7027b368
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991586"
---
# <a name="compiler-warning-level-4-c4125"></a>컴파일러 경고(수준 4) C4125

10진수가 8진수 이스케이프 시퀀스를 마칩니다.

컴파일러가 10진수 없는 8진수를 계산하고 10진수를 문자로 가정합니다.

## <a name="example"></a>예제

```cpp
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

숫자 9가 문자로 사용된 경우 예제를 다음과 같이 수정합니다.

```cpp
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```
