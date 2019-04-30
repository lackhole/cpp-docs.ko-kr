---
title: 컴파일러 오류 C3749
ms.date: 11/04/2016
f1_keywords:
- C3749
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
ms.openlocfilehash: 7535f82a392f3d54b265ada2bd40a8d433838f4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227275"
---
# <a name="compiler-error-c3749"></a>컴파일러 오류 C3749

'attribute': 함수 내에서 사용자 지정 특성을 사용할 수 없습니다

함수 내에서 사용자 지정 특성을 사용할 수 없습니다. 사용자 지정 특성에 대 한 자세한 내용은 항목을 참조 하세요 [특성](../../windows/attributes/attribute.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3749를 생성합니다.

```
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
