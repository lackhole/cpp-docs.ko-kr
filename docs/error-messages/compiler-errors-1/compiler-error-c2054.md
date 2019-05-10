---
title: 컴파일러 오류 C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: 7366995f8930b4733ccff73aef38ebcf65a0c120
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408773"
---
# <a name="compiler-error-c2054"></a>컴파일러 오류 C2054

예상 ' (' 'identifier'를 수행 합니다.

함수 식별자는 닫는 괄호가 필요한 컨텍스트에서 사용 됩니다.

이 오류는 복잡 한 초기화에 등호 (=)를 생략 하 여 발생할 수 있습니다.

다음 샘플에서는 C2054를 생성합니다.

```
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

해결 방법:

```
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```