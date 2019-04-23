---
title: 컴파일러 오류 C3912
ms.date: 11/04/2016
f1_keywords:
- C3912
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
ms.openlocfilehash: bd66196c35715304577b8f6785261be8bdcdafec
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775858"
---
# <a name="compiler-error-c3912"></a>컴파일러 오류 C3912

'event': 형식의 이벤트는 대리자 형식 이어야 합니다.

이벤트 선언 된 하지만 적절 한 형식이 없습니다.

자세한 내용은 [이벤트](../../extensions/event-cpp-component-extensions.md)합니다.

다음 샘플에서는 C3912 오류가 생성 됩니다.

```
// C3912.cpp
// compile with: /clr
delegate void H();
ref class X {
   event int Ev;   // C3912
   event H^ Ev2;   // OK
};
```