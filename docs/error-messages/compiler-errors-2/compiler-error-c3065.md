---
title: 컴파일러 오류 C3065
ms.date: 11/04/2016
f1_keywords:
- C3065
helpviewer_keywords:
- C3065
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
ms.openlocfilehash: e12f6e318d51ecaccc7c29e1e01d1aedcaac937e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404216"
---
# <a name="compiler-error-c3065"></a>컴파일러 오류 C3065

클래스 범위가 아닌 범위에서는 속성을 선언할 수 없습니다.

[property](../../cpp/property-cpp.md) __declspec 한정자가 클래스 외부에서 사용되었습니다.  속성은 클래스 내부에서만 선언할 수 있습니다.

다음 샘플에서는 C3065를 생성합니다.

```
// C3065.cpp
// compile with: /c
__declspec(property(get=get_i)) int i;   // C3065

class x {
public:
   __declspec(property(get=get_i)) int i;   // OK
};
```