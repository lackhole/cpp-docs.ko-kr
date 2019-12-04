---
title: 컴파일러 오류 C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 6faf035c0f4f68b10b187c56bea4cafc776998cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757958"
---
# <a name="compiler-error-c3707"></a>컴파일러 오류 C3707

' function ': 서 수 메서드에는 dispid가 있어야 합니다.

`dispinterface` 메서드를 사용 하는 경우 `dispid`을 할당 해야 합니다. 이 오류를 해결 하려면 아래 샘플의 메서드에 대 한 `id` 특성을 주석 처리 하는 등의 방법으로 `dispinterface` 메서드에 `dispid`을 할당 합니다. 자세한 [내용은 특성 특성](../../windows/dispinterface.md) 및 [id](../../windows/id.md)를 참조 하십시오.

다음 샘플에서는 C3707를 생성 합니다.

```cpp
// C3707.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(name="xx")];
[dispinterface]
__interface IEvents : IDispatch
{
   HRESULT event1([in] int i);   // C3707
   // try the following line instead
   // [id(1)] HRESULT event1([in] int i);
};

int main() {
}
```
