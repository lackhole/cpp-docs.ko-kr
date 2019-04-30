---
title: 컴파일러 오류 C3142
ms.date: 11/04/2016
f1_keywords:
- C3142
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
ms.openlocfilehash: 38bf40b6e1b7495232d7c33317408b872081e9f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374952"
---
# <a name="compiler-error-c3142"></a>컴파일러 오류 C3142

'property_name': 속성의 주소를 가져올 수 없습니다.

속성의 주소를 개발자에 게 사용할 수 없는 경우

다음 샘플에서는 C3142 오류가 생성 됩니다.

```
// C3142_2.cpp
// compile with: /clr
using namespace System;
ref class CSize {
private:
   property int Size {
      int get();
   }
};

int main() {
    &CSize::Size; // C3142
}
```
