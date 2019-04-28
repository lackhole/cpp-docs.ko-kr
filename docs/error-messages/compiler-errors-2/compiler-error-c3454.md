---
title: 컴파일러 오류 C3454
ms.date: 11/04/2016
f1_keywords:
- C3454
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
ms.openlocfilehash: 94c50ccd223567281e02c407e7ee22df75f859d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328603"
---
# <a name="compiler-error-c3454"></a>컴파일러 오류 C3454

[attribute]는 클래스 선언에 사용할 수 없습니다.

클래스는 특성이 되도록 정의되어야 합니다.

자세한 내용은 [attribute](../../windows/attributes/attribute.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3454를 생성합니다.

```
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```