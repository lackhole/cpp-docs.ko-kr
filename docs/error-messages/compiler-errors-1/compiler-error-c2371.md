---
title: 컴파일러 오류 C2371
ms.date: 11/04/2016
f1_keywords:
- C2371
helpviewer_keywords:
- C2371
ms.assetid: d383993d-05ef-4e35-8129-3b58a6f7b7b7
ms.openlocfilehash: 6fe9e85451d973ddd3983a935a9d1349c2699efb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338976"
---
# <a name="compiler-error-c2371"></a>컴파일러 오류 C2371

'identifier': 재정의. 기본 형식이 다릅니다.

식별자가 이미 선언되었습니다.

다음 샘플에서는 C2371을 생성합니다.

```
// C2371.cpp
int main() {
   int i;
   float i;   // C2371, redefinition
   float f;   // OK
}
```