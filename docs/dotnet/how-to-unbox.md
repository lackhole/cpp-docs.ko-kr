---
title: '방법: unbox'
ms.date: 11/04/2016
helpviewer_keywords:
- unboxing
ms.assetid: 75794696-9275-47bf-9a7d-5abe6585ab91
ms.openlocfilehash: ae80497a24b090bc5866b3cfb22748b20adda223
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747945"
---
# <a name="how-to-unbox"></a>방법: unbox

Unbox 값을 수정 하는 방법을 보여 줍니다.

## <a name="example"></a>예제

```
// vcmcppv2_unboxing.cpp
// compile with: /clr
using namespace System;

int main() {
   int ^ i = gcnew int(13);
   int j;
   Console::WriteLine(*i);   // unboxing
   *i = 14;   // unboxing and assignment
   Console::WriteLine(*i);
   j = safe_cast<int>(i);   // unboxing and assignment
   Console::WriteLine(j);
}
```

```Output
13
14
14
```

## <a name="see-also"></a>참고자료

[Boxing](../windows/boxing-cpp-component-extensions.md)
