---
title: 컴파일러 오류 C3189
ms.date: 11/04/2016
f1_keywords:
- C3189
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
ms.openlocfilehash: 2b53056cf8a7b4b9b49720ef17e8f9318390059a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761623"
---
# <a name="compiler-error-c3189"></a>컴파일러 오류 C3189

' typeid\<type abstract 선언 자 > ':이 구문은 더 이상 지원 되지 않습니다. 대신:: typeid를 사용 하십시오.

사용 되지 않는 [typeid](../../extensions/typeid-cpp-component-extensions.md) 형식이 사용 되었습니다. 새 양식을 사용 합니다.

다음 샘플에서는 C3189를 생성 합니다.

```cpp
// C3189.cpp
// compile with: /clr
int main() {
   System::Type^ t  = typeid<System::Object>;   // C3189
   System::Type^ t2  = System::Object::typeid;   // OK
}
```
