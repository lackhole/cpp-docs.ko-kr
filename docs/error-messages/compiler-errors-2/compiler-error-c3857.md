---
title: 컴파일러 오류 C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 1270d09c870bfdf9f390d6afb1625ad3e99e01a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265440"
---
# <a name="compiler-error-c3857"></a>컴파일러 오류 C3857

'type': 여러 형식 매개 변수 목록을 사용할 수 없습니다

여러 개의 템플릿 또는 제네릭 자세히 허용 되지 않는 동일한 형식에 대해 지정 되었습니다.

다음 샘플에서는 C3857를 생성합니다.

```
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

해결 방법:

```
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857은 제네릭을 사용할 때도 발생할 수 있습니다.

```
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

해결 방법:

```
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```