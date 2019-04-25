---
title: 컴파일러 오류 C3237
ms.date: 11/04/2016
f1_keywords:
- C3237
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
ms.openlocfilehash: 9853fd67c2b053e337cfacb5478e206c79321263
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173329"
---
# <a name="compiler-error-c3237"></a>컴파일러 오류 C3237

'generic_class': 제네릭 클래스는 사용자 지정 특성이 될 수 없습니다.

제네릭 클래스는 사용자 정의 특성이 될 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3237을 생성합니다.

```
// C3237.cpp
// compile with: /clr /c
// C3237 expected
using namespace System;

generic <class T>
// Delete the following line to resolve.
[attribute(AttributeTargets::All, AllowMultiple=true)]
public ref class GR {};
```