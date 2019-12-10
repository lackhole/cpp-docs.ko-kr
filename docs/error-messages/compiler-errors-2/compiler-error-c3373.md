---
title: 컴파일러 오류 C3373
ms.date: 11/04/2016
f1_keywords:
- C3373
helpviewer_keywords:
- C3373
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
ms.openlocfilehash: cbf6b19e6ae5e5278d7536ba8ec1cfc28483f753
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758582"
---
# <a name="compiler-error-c3373"></a>컴파일러 오류 C3373

'attribute' 특성은 coclass의 경우를 제외하고 인수를 사용하지 않습니다.

일부 특성은 둘 이상의 C++ 구문에 적용할 수 있지만 특성의 인수는 일부 구문에서만 사용할 수 있습니다.

다음 샘플에서는 C3373을 생성합니다.

```cpp
// C3373.cpp
#include <windows.h>

[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface
{
   // arguments to source and restricted are not allowed when
   // these attributes are applied to an interface
   [source(IMyIface)] HRESULT f1();
   [restricted(IMyIface)] HRESULT f2(); // C3373
};

[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ]
class CMyClass : public IMyIface {
};

int main() {
}
```
