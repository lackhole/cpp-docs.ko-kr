---
title: 컴파일러 오류 C2726
ms.date: 11/04/2016
f1_keywords:
- C2726
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
ms.openlocfilehash: d0ade9317c996bb3432e7a4626fc930a3d5df349
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208391"
---
# <a name="compiler-error-c2726"></a>컴파일러 오류 C2726

'gcnew'는 WinRT 또는 관리되는 형식의 개체를 만드는 데만 사용할 수 있습니다.

가비지 수집된 힙에 네이티브 형식의 인스턴스를 만들 수 없습니다.

다음 샘플에서는 C2726 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C2726.cpp
// compile with: /clr
using namespace System;
class U {};
ref class V {};
value class W {};

int main() {
   U* pU = gcnew U;    // C2726
   U* pU2 = new U;   // OK
   V^ p2 = gcnew V;   // OK
   W p3;   // OK

}
```
