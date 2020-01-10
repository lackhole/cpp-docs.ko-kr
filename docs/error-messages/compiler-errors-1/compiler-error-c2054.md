---
title: 컴파일러 오류 C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: e7d90d684c1d95f540f6357bf61ee7c6f889ad3f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302057"
---
# <a name="compiler-error-c2054"></a>컴파일러 오류 C2054

' identifier '를 따르려면 ' ('가 필요 합니다.

함수 식별자는 후행 괄호가 필요한 컨텍스트에서 사용 됩니다.

이 오류는 복잡 한 초기화에서 등호 (=)를 생략 하 여 발생할 수 있습니다.

다음 샘플에서는 C2054를 생성 합니다.

```c
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

가능한 해결 방법:

```c
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```
