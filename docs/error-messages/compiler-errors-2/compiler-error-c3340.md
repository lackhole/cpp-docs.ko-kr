---
title: 컴파일러 오류 C3340
ms.date: 11/04/2016
f1_keywords:
- C3340
helpviewer_keywords:
- C3340
ms.assetid: 23b12298-b92a-4717-8380-f165c998cb8a
ms.openlocfilehash: 1eff84ec133b55ddc3df98364c7d8542be398a69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300689"
---
# <a name="compiler-error-c3340"></a>컴파일러 오류 C3340

'interface': 인터페이스는 coclass 'class'에서 'restricted'이면서 'default'일 수 없습니다.

[restricted](../../windows/restricted.md) 특성 및 [default](../../windows/default-cpp.md) 특성은 함께 사용할 수 없습니다.

다음 샘플에서는 C3340을 생성합니다.

```
// C3340.cpp
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface
{
   HRESULT f1();
};

[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f),
default(IMyIface),
source(IMyIface),restricted(IMyIface) ]
class CmyClass // C3340
{
};

int main()
{
}
```