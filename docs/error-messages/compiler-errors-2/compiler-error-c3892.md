---
title: 컴파일러 오류 C3892
ms.date: 11/04/2016
f1_keywords:
- C3892
helpviewer_keywords:
- C3892
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
ms.openlocfilehash: 07f34efa4ecf1445665fccf60dba10ea12dbff3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281588"
---
# <a name="compiler-error-c3892"></a>컴파일러 오류 C3892

'var': const 인 변수에 할당할 수 없습니다.

Const 변수를 선언 하 고 초기화 한 후에 변경할 수 없습니다.

다음 샘플에서는 C3892 오류가 생성 됩니다.

```
// C3892.cpp
// compile with: /clr
ref struct Y1 {
   static const int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3892
}
```