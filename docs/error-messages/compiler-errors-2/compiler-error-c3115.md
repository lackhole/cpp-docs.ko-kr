---
title: 컴파일러 오류 C3115
ms.date: 11/04/2016
f1_keywords:
- C3115
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
ms.openlocfilehash: c03361f08ffd54396d307ed8c075a327c576d49b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760741"
---
# <a name="compiler-error-c3115"></a>컴파일러 오류 C3115

' attribute ':이 특성은 ' 생성 '에 사용할 수 없습니다.

특성이 의도 하지 않은 구문에 적용 되었습니다.  자세한 내용은 [사용 별 특성](../../windows/attributes/attributes-by-usage.md) 을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3115를 생성 합니다.

```cpp
// C3115.cpp
// compile with: /c
#include <unknwn.h>
[module(name="xx")];

[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115
// try the following line instead
// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI {
   HRESULT xx();
};
```
