---
title: 컴파일러 오류 C3860
ms.date: 11/04/2016
f1_keywords:
- C3860
helpviewer_keywords:
- C3860
ms.assetid: 1fb5110d-594e-4f1c-8773-888233af1313
ms.openlocfilehash: 89b43c03cb26fa48d347f6066a18ae36c54234db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352977"
---
# <a name="compiler-error-c3860"></a>컴파일러 오류 C3860

형식 인수 목록에 클래스 형식 이름 다음에 매개 변수 형식 매개 변수 목록에 사용 되는 순서 대로 나열 해야 합니다.

제네릭 또는 템플릿 인수 목록 형식이 잘못 되었습니다.

다음 샘플에서는 C3860를 생성합니다.

```
// C3860.cpp
// compile with: /LD
template <class T1, class T2>
struct A {
   void f();
};

template <class T2, class T1>
void A<T1, T2>::f() {}   // C3860
```

해결 방법:

```
// C3860b.cpp
// compile with: /c
template <class T1, class T2>
struct A {
   void f();
};

template <class T2, class T1>
void A<T2, T1>::f() {}
```

C3860은 제네릭을 사용할 때도 발생할 수 있습니다.

```
// C3860c.cpp
// compile with: /clr
generic<class T,class U>
ref struct GC {
   void f();
};

generic<class T, class U>
void GC<T,T>::f() {}   // C3860
```

해결 방법:

```
// C3860d.cpp
// compile with: /clr /c
generic<class T,class U>
ref struct GC {
   void f();
};

generic<class T, class U>
void GC<T,U>::f() {}
```