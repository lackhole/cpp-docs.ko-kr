---
title: 컴파일러 경고 (수준 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: bfe54fc40b4d6927a1d75f529ec9b619f9b29226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397369"
---
# <a name="compiler-warning-level-1-c4028"></a>컴파일러 경고 (수준 1) C4028

정식 매개 변수 'number' 선언과 다릅니다.

정식 매개 변수 형식의 선언에 해당 매개 변수를 사용 하 여 일치 하지 않습니다. 원래 선언에서 형식이 사용 됩니다.

이 경고 C 소스 코드에만 유효합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4028 오류가 발생 합니다.

```
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```