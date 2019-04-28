---
title: 컴파일러 오류 C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 622e7366dda4cd6693d9b6128855fa0966e07952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222481"
---
# <a name="compiler-error-c3320"></a>컴파일러 오류 C3320

'type': 형식은 모듈의 'name' 속성과 같은 이름을 사용할 수 없습니다.

에 전달 된 매개 변수는 내보낸된 사용자 정의 형식 (UDT), 구조체, 클래스, 열거형 또는 공용 구조체 수 있는 동일한 이름을 사용할 수 없습니다는 [모듈](../../windows/module-cpp.md) 특성의 name 속성입니다.

## <a name="example"></a>예제

다음 샘플에서는 C3320을 생성합니다.

```cpp
// C3320.cpp
#include "unknwn.h"
[module(name="xx")];

[export] struct xx {   // C3320
// Try the following line instead
// [export] struct yy {
   int i;
};
```