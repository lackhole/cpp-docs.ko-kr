---
title: 컴파일러 오류 C3763
ms.date: 11/04/2016
f1_keywords:
- C3763
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
ms.openlocfilehash: e7dc73334cedda27b82f79b1d2b7a8fc38a8098d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400268"
---
# <a name="compiler-error-c3763"></a>컴파일러 오류 C3763

'type': 'retval' 및 'out' 데이터 포인터 형식에만 나타날 수 있습니다

합니다 [아웃](../../windows/out-cpp.md) 하거나 [retval](../../windows/retval.md) 특성에 대 한 형식 포인터의 매개 변수에 나타날 수 있습니다. 특성을 제거 하거나 형식 포인터의 매개 변수를 확인 합니다.

다음 샘플에서는 C3763 오류가 생성 됩니다.

```
// C3763.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlplus.h>
#include <atlcom.h>

[ module(name=test) ];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IF84 : IDispatch
{
   [id(0x00000002)]HRESULT m2([out]unsigned char);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class CF84 : public IF84
{   // C3763
public:
   HRESULT __stdcall m2(unsigned char i)
   {
      return S_OK;
   }
};

int main()
{
}
```