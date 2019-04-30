---
title: 컴파일러 경고(수준 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 28b3e49717993a3bf20c8cfec5938d698266c0f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406537"
---
# <a name="compiler-warning-level-1-c4804"></a>컴파일러 경고(수준 1) C4804

'operation': 안전 하지 않은 작업에 사용 되는 ' bool' 형식 사용

이 경고는 사용할 때를 `bool` 변수 또는 예기치 않은 방식으로 값입니다. 예를 들어, C4804 단항 부정 연산자와 같은 연산자를 사용 하는 경우 생성 됩니다 (**-**) 또는 보수 연산자 (`~`). 컴파일러가 식을 평가합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4804 오류가 생성 됩니다.

```
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```