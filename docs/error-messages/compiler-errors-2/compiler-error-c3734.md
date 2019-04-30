---
title: 컴파일러 오류 C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: 78b3d1a57d358eb11ba2f01ec184c5487a578228
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327927"
---
# <a name="compiler-error-c3734"></a>컴파일러 오류 C3734

'class': 관리되는 클래스 또는 WinRT 클래스에는 coclass를 사용할 수 없습니다.

합니다 [coclass](../../windows/coclass.md) 특성을 사용 하 여 사용할 수 없습니다 관리 되는 또는 WinRT 클래스입니다.

다음 샘플에서는 C3734를 생성하고 해결 방법을 보여 줍니다.

```
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
