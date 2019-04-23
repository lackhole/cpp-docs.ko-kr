---
title: 컴파일러 오류 C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: 00e103720dc666b17566b67da19d4e908bb3addd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776082"
---
# <a name="compiler-error-c3896"></a>컴파일러 오류 C3896

'member': 잘못 된 이니셜라이저:이 리터럴 데이터 멤버 'nullptr'를 사용 하 여 초기화할 수 있습니다

A [리터럴](../../extensions/literal-cpp-component-extensions.md) 데이터 멤버 잘못 초기화 되었습니다.  참조 [nullptr](../../extensions/nullptr-cpp-component-extensions.md) 자세한 내용은 합니다.

다음 샘플에서는 C3896 오류가 생성 됩니다.

```
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```