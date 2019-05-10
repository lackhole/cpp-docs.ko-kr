---
title: 컴파일러 경고(수준 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: e9ad30f60260893130beed921aab811c894868cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402504"
---
# <a name="compiler-warning-level-2-c4307"></a>컴파일러 경고(수준 2) C4307

'operator': 정수 계열 상수가 오버플로 됩니다.

연산자는 정수 상수에 할당 된 공간에 오버플로가 발생 하는 식에 사용 됩니다. 상수에 대 한 더 큰 형식을 사용 해야 합니다. **int 서명** 보다 작은 값을 저장를 `unsigned int` 때문에 **int 서명** 부호를 나타내는 1 비트를 사용 합니다.

다음 샘플에서는 C4307 오류가 생성 됩니다.

```
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```