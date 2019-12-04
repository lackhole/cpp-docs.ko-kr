---
title: 컴파일러 오류 C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: 44b41dd706c7eb290c71d7312464d688cbcf08d3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757360"
---
# <a name="compiler-error-c3363"></a>컴파일러 오류 C3363

'type': 'typeid'는 형식에만 적용될 수 있습니다.

[typeid](../../extensions/typeid-cpp-component-extensions.md) 연산자를 잘못 사용했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3363을 생성합니다.

```cpp
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```
