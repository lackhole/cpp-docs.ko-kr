---
title: 컴파일러 오류 C2989
ms.date: 11/04/2016
f1_keywords:
- C2989
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
ms.openlocfilehash: e5f03d644ab6c25b7eb0da0dc1684c7de5c2e6a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366136"
---
# <a name="compiler-error-c2989"></a>컴파일러 오류 C2989

'class': 클래스 형식이 이미 비 클래스 형식으로 선언 되었습니다

제네릭 클래스 또는 템플릿 템플릿이나 제네릭이 아닌 클래스를 재정의합니다. 충돌에 대 한 헤더 파일을 확인 합니다.

다음 샘플에서는 C2989를 생성합니다.

```cpp
// C2989.cpp
// compile with: /c
class C{};

template <class T>
class C{};  // C2989
class C2{};
```

C2989는 제네릭을 사용할 때도 발생할 수 있습니다.

```cpp
// C2989b.cpp
// compile with: /clr /c
ref class GC1;

generic <typename T> ref class GC1;   // C2989
template <typename T> ref class GC2;

generic <typename T> ref class GC2;   // C2989
generic <typename T> ref class GCb;
template <typename T> ref class GC2;
generic <typename T> ref class GCc;
```