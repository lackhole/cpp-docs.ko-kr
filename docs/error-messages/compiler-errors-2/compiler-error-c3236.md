---
title: 컴파일러 오류 C3236
ms.date: 11/04/2016
f1_keywords:
- C3236
helpviewer_keywords:
- C3236
ms.assetid: 4ef1871f-a348-44ae-922b-1e2081de20d0
ms.openlocfilehash: 2bcc9aa2c1b179caf6c7fc51ba86cdc4e56b0a5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175513"
---
# <a name="compiler-error-c3236"></a>컴파일러 오류 C3236

제네릭을 명시적으로 인스턴스화할 수 없습니다.

컴파일러는 제네릭 클래스의 명시적 인스턴스화를 허용하지 않습니다.

다음 샘플에서는 C3236을 생성합니다.

```
// C3236.cpp
// compile with: /clr
generic<class T>
public ref class X {};

generic ref class X<int>;   // C3236
```

다음 샘플에는 가능한 해결 방법을 보여 줍니다.

```
// C3236b.cpp
// compile with: /clr /c
generic<class T>
public ref class X {};
```