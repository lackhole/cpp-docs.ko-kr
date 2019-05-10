---
title: 컴파일러 오류 C3890
ms.date: 11/04/2016
f1_keywords:
- C3890
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
ms.openlocfilehash: 2354be5ac7299fc0361e1b3ad50554e9949f8c1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385552"
---
# <a name="compiler-error-c3890"></a>컴파일러 오류 C3890

'var': 리터럴 데이터 멤버의 주소를 가져올 수 없습니다.

리터럴 데이터 멤버는 가비지 수집 힙에 존재합니다.  주소는 유용 하므로 가비지 수집 힙에 있는 개체를 이동할 수 있습니다.

다음 샘플에서는 C3890 오류가 생성 됩니다.

```
// C3890.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   int p = &Y1::staticConst;   // C3890
   int p2 = Y1::staticConst;   // OK
}
```