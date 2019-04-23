---
title: 컴파일러 오류 C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: a3c69b05e22c2d267ad07f19a0d0ab60f3eebb94
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777356"
---
# <a name="compiler-error-c3625"></a>컴파일러 오류 C3625

'native_type': 네이티브 형식은 WinRT 또는 관리되는 형식 'type'에서 파생될 수 없습니다.

네이티브 클래스는 WinRT 또는 관리되는 클래스에서 상속할 수 없습니다. 자세한 내용은 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3625 오류가 발생하는 경우를 보여 줍니다.

```
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
