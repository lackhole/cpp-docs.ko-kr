---
title: 컴파일러 오류 C3718
ms.date: 11/04/2016
f1_keywords:
- C3718
helpviewer_keywords:
- C3718
ms.assetid: 346b5205-c44d-49d3-b66a-96417d3d6986
ms.openlocfilehash: d0bcf784f5b522d05585d63a3b38a2befb5aa191
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753200"
---
# <a name="compiler-error-c3718"></a>컴파일러 오류 C3718

수신 하는 클래스의 멤버 함수 컨텍스트에서만 ' event '를 호출할 수 있습니다.

`event`는 수신 클래스 에서만 호출할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3718를 생성 합니다.

```cpp
// C3718.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="test")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I
{
    HRESULT f();
};

[event_source(com), coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct E
{
    __event __interface I;
};

[event_receiver(com)]
struct R
{
    void b()
    {
        printf_s("B::bar()\n");
    }

    void HookAndRun(E* pE)
    {
        __hook(&I::f, pE->GetUnknown(), &R::b);
        __raise pE->f();
    }
};

int main()
{
    CComObject<E>* pE;
    CComObject<E>::CreateInstance(&pE);

    __hook(&I::f, pE->GetUnknown(), &R::b, &r);   // C3718
    __raise pE->f();
    // try the following lines instead
    // R r;
    // r.HookAndRun(pE);
}
```
