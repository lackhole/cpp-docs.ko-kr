---
title: 컴파일러 오류 C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 8a1525539c84ea427815a03057bb6d2f9213fec7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328525"
---
# <a name="compiler-error-c3707"></a>컴파일러 오류 C3707

'function': dispinterface 메서드에 dispid가 있어야 합니다.

사용 하는 경우는 `dispinterface` 메서드를 할당 해야 하는 `dispid`합니다. 이 오류를 해결 하려면 할당을 `dispid` 에 `dispinterface` 등의 주석 처리를 제거 하는 방법에 대 한 메서드를는 `id` 아래 샘플의 메서드에 대 한 특성입니다. 자세한 내용은 특성을 참조 하세요 [dispinterface](../../windows/dispinterface.md) 하 고 [id](../../windows/id.md)합니다.

다음 샘플에서는 C3707를 생성합니다.

```
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