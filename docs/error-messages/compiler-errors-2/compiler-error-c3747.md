---
title: 컴파일러 오류 C3747
ms.date: 11/04/2016
f1_keywords:
- C3747
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
ms.openlocfilehash: 860a990e35b0d51dfc1316a11a2d2512eb40c273
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226798"
---
# <a name="compiler-error-c3747"></a>컴파일러 오류 C3747

기본 형식 매개 변수가 없습니다: 매개 변수 매개 변수

기본값이 있는 제네릭 또는 템플릿 매개 변수에 기본값이 없는 매개 변수에 따라 매개 변수 목록에서 올 수 없습니다.

다음 샘플에서는 C3747를 생성합니다.

```
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

해결 방법:

```
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```