---
title: 컴파일러 경고(수준 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: c5ffa07b06f010d10edc14aa7576bb614aa9dd04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401035"
---
# <a name="compiler-warning-level-4-c4238"></a>컴파일러 경고(수준 4) C4238

비표준 확장이 사용 됨: 클래스 rvalue를 lvalue로 사용

시각적 개체의 이전 버전과 호환성에 대 한 C++에 대 한 Microsoft 확장 (**/Ze**) 컨텍스트에서 rvalue는 암시적 또는 명시적으로 해당 주소를 사용 하는 대로 클래스 형식을 사용할 수 있습니다. 다음 예제와 같은 일부 경우 위험할 수 있습니다.

## <a name="example"></a>예제

```
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

이러한 사용은 ANSI 규격 오류 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).