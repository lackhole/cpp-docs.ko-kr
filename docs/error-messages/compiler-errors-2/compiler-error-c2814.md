---
title: 컴파일러 오류 C2814
ms.date: 11/04/2016
f1_keywords:
- C2814
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
ms.openlocfilehash: 5cc22afa29160ce50d658a4a8d4b2a56e5145527
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750860"
---
# <a name="compiler-error-c2814"></a>컴파일러 오류 C2814

'member' : 네이티브 형식은 관리되는 형식 또는 WinRT 형식 'type' 내부에 중첩될 수 없습니다.

## <a name="example"></a>예제

네이티브 형식은 CLR 또는 WinRT 형식에 중첩할 수 없습니다. 다음 샘플에서는 C2814 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2814.cpp
// compile with: /clr /c
ref class A {
   class B {};   // C2814
   ref class C {};   // OK
};
```
