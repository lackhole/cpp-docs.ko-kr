---
title: 컴파일러 오류 C3372
ms.date: 11/04/2016
f1_keywords:
- C3372
helpviewer_keywords:
- C3372
ms.assetid: 38ee39ed-03ff-4e6d-9104-f1977b96645d
ms.openlocfilehash: f410e18621c6784de011d12b45d07c163afdb1c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400346"
---
# <a name="compiler-error-c3372"></a>컴파일러 오류 C3372

coclass의 'source' 특성에 대한 인터페이스를 하나 이상 지정해야 합니다.

특정 특성의 경우 인터페이스 이름을 매개 변수로 전달해야 합니다.

다음 샘플에서는 C3372를 생성합니다.

```
// C3372.cpp
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface {
   HRESULT f1();
};
// to resolve, pass an interface name to the source attribute
// for example, source(IMyIface)
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), source,
  default(IMyIface) ] // C3372
class CMyClass {
};

int main() {
}
```