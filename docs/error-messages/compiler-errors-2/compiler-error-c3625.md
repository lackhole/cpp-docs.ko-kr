---
title: 컴파일러 오류 C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: 83b6756c75f90380024a8f31df62290bed1f7738
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761909"
---
# <a name="compiler-error-c3625"></a>컴파일러 오류 C3625

'native_type': 네이티브 형식은 WinRT 또는 관리되는 형식 'type'에서 파생될 수 없습니다.

네이티브 클래스는 WinRT 또는 관리되는 클래스에서 상속할 수 없습니다. 자세한 내용은 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md)를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3625 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
