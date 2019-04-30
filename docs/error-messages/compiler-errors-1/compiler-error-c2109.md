---
title: 컴파일러 오류 C2109
ms.date: 11/04/2016
f1_keywords:
- C2109
helpviewer_keywords:
- C2109
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
ms.openlocfilehash: 6592f36b29fe643e088669089b1af1b69b7b2125
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364755"
---
# <a name="compiler-error-c2109"></a>컴파일러 오류 C2109

아래 첨자 배열 또는 포인터 형식이 필요

첨자는 배열 없는 변수에 사용 되었습니다.

다음 샘플에서는 C2109 오류가 생성 됩니다.

```
// C2109.cpp
int main() {
   int a, b[10] = {0};
   a[0] = 1;   // C2109
   b[0] = 1;   // OK
}
```