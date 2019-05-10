---
title: 컴파일러 오류 C2087
ms.date: 11/04/2016
f1_keywords:
- C2087
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
ms.openlocfilehash: 11d5a0a86ba399e28a641fa490f19be020db2d9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301437"
---
# <a name="compiler-error-c2087"></a>컴파일러 오류 C2087

'identifier': 첨자가 없습니다

여러 첨자가 포함 된 배열을 정의 1 보다 더 높은 차원의 첨자 값이 없습니다.

다음 샘플에서는 C2087 오류가 생성 됩니다.

```
// C2087.cpp
int main() {
   char a[10][];   // C2087
}
```

해결 방법:

```
// C2087b.cpp
int main() {
   char b[4][5];
}
```