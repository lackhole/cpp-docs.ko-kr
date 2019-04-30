---
title: 컴파일러 오류 C2955
ms.date: 03/28/2017
f1_keywords:
- C2955
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
ms.openlocfilehash: c012e5189b9ca1d0b0e786cbddacedee7c6728d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300741"
---
# <a name="compiler-error-c2955"></a>컴파일러 오류 C2955

'identifier' : 클래스 템플릿 또는 별칭 제네릭을 사용하려면 템플릿 또는 제네릭 인수 목록이 필요합니다.

템플릿 또는 제네릭 인수 목록이 없으면 클래스 템플릿 또는 클래스 제네릭을 식별자로 사용할 수 없습니다.

자세한 내용은 [클래스 템플릿을](../../cpp/class-templates.md)합니다.

다음 샘플에서는 C2955 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C2955.cpp
// compile with: /c
template<class T>
class X {};

X x1;   // C2955
X<int> x2;   // OK - this is how to fix it.
```

클래스 템플릿에 선언된 함수에 대해 아웃오브 라인 정의를 만들 때도 C2955가 발생할 수 있습니다.

```
// C2955_b.cpp
// compile with: /c
template <class T>
class CT {
public:
   void CTFunc();
   void CTFunc2();
};

void CT::CTFunc() {}   // C2955

// OK - this is how to fix it
template <class T>
void CT<T>::CTFunc2() {}
```

제네릭을 사용할 때도 C2955가 발생할 수 있습니다.

```
// C2955_c.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC^ g;   // C2955
   GC <int>^ g;
}
```

## <a name="example"></a>예제

**Visual Studio 2017 이상:** 컴파일러는 올바르게 서식 파일 (예를 들어의 일부로 기본 템플릿 인수 또는 비형식 템플릿 매개 변수) 템플릿 매개 변수 목록에 표시 되 면 누락 된 템플릿 인수 목록을 진단 합니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 오류를 생성합니다.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```
