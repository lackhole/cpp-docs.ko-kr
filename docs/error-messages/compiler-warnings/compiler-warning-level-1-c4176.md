---
title: 컴파일러 경고(수준 1) C4176
ms.date: 11/04/2016
f1_keywords:
- C4176
helpviewer_keywords:
- C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
ms.openlocfilehash: 6e0f7ab75309994ab306f5caed54724f32e388b1
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624796"
---
# <a name="compiler-warning-level-1-c4176"></a>컴파일러 경고(수준 1) C4176

'subcomponent': #pragma 구성 요소 브라우저의 하위 구성 요소를 알 수 없습니다.

**구성 요소** pragma에 잘못된 하위 구성 요소가 포함되어 있습니다. 특정 이름에 대한 참조를 제외하려면 이름 앞에 **참조** 옵션을 사용해야 합니다.

## <a name="example"></a>예제

```cpp
// C4176.cpp
// compile with: /W1 /LD
#pragma component(browser, off, i)  // C4176
#pragma component(browser, off, references, i) // ok
```