---
title: 컴파일러 오류 C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: 381bb59dae523c05cdc67e33ba9d326e247abc7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752862"
---
# <a name="compiler-error-c3734"></a>컴파일러 오류 C3734

'class': 관리되는 클래스 또는 WinRT 클래스에는 coclass를 사용할 수 없습니다.

[Coclass](../../windows/coclass.md) 특성은 관리 되는 클래스 또는 WinRT 클래스와 함께 사용할 수 없습니다.

다음 샘플에서는 C3734를 생성하고 해결 방법을 보여 줍니다.

```cpp
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
