---
title: 컴파일러 오류 C2896
ms.date: 11/04/2016
f1_keywords:
- C2896
helpviewer_keywords:
- C2896
ms.assetid: b600407b-cb05-42e3-9069-2aa6960f0eaa
ms.openlocfilehash: 1e30dc17e7c143af52c5a8b56be7f1efa7632ee2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227412"
---
# <a name="compiler-error-c2896"></a>컴파일러 오류 C2896

'function1': 함수 템플릿을 'function2' 인수로 사용할 수 없습니다

함수 템플릿에 다른 함수 템플릿 인수로 일 수 없습니다.

다음 샘플에서는 C2896 오류가 생성 됩니다.

```
// C2896.cpp
template<class T1, class T2> void f1(void(*)(T1, T2));
template<class T1, class T2> void f2(T1, T2);

int main() {
   f1(f2);   // C2896
}
```

C2896은 제네릭을 사용 하는 경우에 발생할 수 있습니다.

```
// C2896b.cpp
// compile with: /clr
generic<class T1> void gf1(T1){}
generic<class T1> void gf2(T1){}

int main() {
   gf1(gf2);   // C2896
   gf1(1);   // OK
}
```