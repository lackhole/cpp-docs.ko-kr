---
title: 컴파일러 오류 C3749
ms.date: 11/04/2016
f1_keywords:
- C3749
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
ms.openlocfilehash: 75138bf8b090b7770d5bee918790efc095d76627
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761844"
---
# <a name="compiler-error-c3749"></a>컴파일러 오류 C3749

' attribute ': 사용자 지정 특성은 함수 내에서 사용할 수 없습니다.

사용자 지정 특성은 함수 내에서 사용할 수 없습니다. 사용자 지정 특성에 대 한 자세한 내용은 항목 [특성](../../windows/attributes/attribute.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3749를 생성 합니다.

```cpp
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
