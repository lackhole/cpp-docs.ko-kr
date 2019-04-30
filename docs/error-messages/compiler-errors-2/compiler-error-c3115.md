---
title: 컴파일러 오류 C3115
ms.date: 11/04/2016
f1_keywords:
- C3115
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
ms.openlocfilehash: e334836986548d4f854dd9a5760bd8315b769d03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404093"
---
# <a name="compiler-error-c3115"></a>컴파일러 오류 C3115

'attribute':이 특성은 'construct'에서 허용 되지 않습니다

특성은 의도 하지 않은 구문에 적용 되었습니다.  참조 [용도별 특성](../../windows/attributes/attributes-by-usage.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C3115를 생성합니다.

```
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