---
title: 컴파일러 오류 C2914
ms.date: 11/04/2016
f1_keywords:
- C2914
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
ms.openlocfilehash: 2500736f799032aea71173931139404b4406a16a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384350"
---
# <a name="compiler-error-c2914"></a>컴파일러 오류 C2914

'identifier': 함수 인수가 모호 하기 때문으로 형식 인수를 추론할 수 없습니다.

컴파일러는 제네릭 또는 템플릿 인수에 사용할 함수를 오버 로드 된 확인할 수 없습니다.

다음 샘플에서는 C2914 오류가 생성 됩니다.

```
// C2914.cpp
// compile with: /c
void f(int);
void f(double);
template<class T> void g(void (*) (T));
void h() { g(f); }   // C2914
// try the following line instead
// void h() { g<int>(f); }
```

C2914는 제네릭을 사용할 때도 발생할 수 있습니다.  다음 샘플에서는 C2914 오류가 생성 됩니다.

```
// C2914b.cpp
// compile with: /clr /c
void f(int);
void f(double);

template<class T>
void gf(void (*) (T));

void h() { gf(f);}   // C2914
// try the following line instead
void h() { gf<int>(f); }
```