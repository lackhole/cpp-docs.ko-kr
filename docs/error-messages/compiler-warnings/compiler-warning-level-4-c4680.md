---
title: 컴파일러 경고(수준 4) C4680
ms.date: 11/04/2016
f1_keywords:
- C4680
helpviewer_keywords:
- C4680
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
ms.openlocfilehash: 9130fa2665452b85c5ec83eef0b3d1d618c995a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226871"
---
# <a name="compiler-warning-level-4-c4680"></a>컴파일러 경고(수준 4) C4680

'class': coclass는 기본 인터페이스를 지정 하지 않습니다

A [기본](../../windows/default-cpp.md) 로 표시 된 클래스에 대 한 인터페이스를 지정 하지 않았습니다 합니다 [coclass](../../windows/coclass.md) 특성입니다. 유용 하 게 개체에 대 한 순서 대로 인터페이스를 구현 해야 합니다.

다음 샘플에서는 C4680 오류가 생성 됩니다.

```
// C4680.cpp
// compile with: /W4
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface1
{
   HRESULT f1();
};

[ object, uuid(37331a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface2
{
   HRESULT f1();
};

// to resolve C4680, specify a source interface also
// for example, default(IMyIface1, IMyface2)
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), default(IMyIface1), source(IMyIface1) ]
class CMyClass : public IMyIface1
{   // C4680
};

int main()
{
}
```