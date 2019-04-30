---
title: 컴파일러 오류 C2867
ms.date: 11/04/2016
f1_keywords:
- C2867
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
ms.openlocfilehash: 3c79fec9f52ea9451cea456dcc062af9bcbe9b3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164973"
---
# <a name="compiler-error-c2867"></a>컴파일러 오류 C2867

'identifier': 네임 스페이스가 아닙니다

`using` 지시문은 네임 스페이스 이외의 항목에 적용 되었습니다.

다음 샘플에서는 C2867 오류가 생성 됩니다.

```
// C2867.cpp
// compile with: /c
namespace N {
   class X {};
}
using namespace N::X;   // C2867
```