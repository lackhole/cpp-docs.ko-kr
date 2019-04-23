---
title: 컴파일러 경고(수준 1) C4393
ms.date: 11/04/2016
f1_keywords:
- C4393
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
ms.openlocfilehash: 4226c8ecd41e890d70fa5741decae605d45b620f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777044"
---
# <a name="compiler-warning-level-1-c4393"></a>컴파일러 경고(수준 1) C4393

'var': const 리터럴 데이터 멤버에 영향을 주지 무시

A [리터럴](../../extensions/literal-cpp-component-extensions.md) 데이터 멤버를 const로 지정 합니다.  리터럴 데이터 멤버를 const 의미 하므로 없습니다 필요가 추가 선언에 const를 합니다.

다음 샘플에서는 C4393 오류가 생성 됩니다.

```
// C4393.cpp
// compile with: /clr /W1 /c
ref struct Y1 {
   literal const int staticConst = 10;   // C4393
   literal int staticConst2 = 10;   // OK
};
```