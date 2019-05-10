---
title: 컴파일러 오류 C2059
ms.date: 03/26/2019
f1_keywords:
- C2059
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
ms.openlocfilehash: 2fb2aa86a1fd8f8e0710d787682fdd44abd941ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408669"
---
# <a name="compiler-error-c2059"></a>컴파일러 오류 C2059

syntax error : 'token'

토큰 구문 오류가 발생합니다.

다음 예제에서는 선언 하는 줄에 대 한 오류 메시지가 생성 `j`합니다.

```
// C2059e.cpp
// compile with: /c
// C2143 expected
// Error caused by the incorrect use of '*'.
   int j*; // C2059
```

에 오류의 원인을 확인 하려면 오류 메시지에 나열 된 줄 뿐만 아니라 위에 있는 줄을 검사 합니다. 그래도 줄을 검사 하는 문제에 대 한 아무런 단서를, 오류 메시지에 나열 된 선과 상위 아마도 여러 줄 주석으로 처리 합니다.

오류 메시지 바로 뒤에 오는 기호에서 발생 하는 경우는 `typedef` 변수인 변수의 소스 코드에 정의 되어 있는지 확인 합니다.

C2059 전처리기 기호 이름을 식별자로 다시 사용할 때 발생 합니다. 다음 예에서 컴파일러는 다음과 같이 표시 됩니다. `DIGITS.ONE` 번호 1로 유효 하지 않은 열거형 요소 이름으로:

```cpp
#define ONE 1

enum class DIGITS {
    ZERO,
    ONE // error C2059
};
```

C2059 오류가 발생할 수 있으므로, nothing으로 계산 되는 기호 때 **/D**_기호_ **=** 컴파일하는 데 사용 됩니다.

```
// C2059a.cpp
// compile with: /DTEST=
#include <stdio.h>

int main() {
   #ifdef TEST
      printf_s("\nTEST defined %d", TEST);   // C2059
   #else
      printf_s("\nTEST not defined");
   #endif
}
```

C2059 발생할 수 있는 또 다른 경우에는 기본 인수는 함수에 구조체를 지정 하는 응용 프로그램을 컴파일할 때. 인수에 대 한 기본 값 식 이어야 합니다. 이니셜라이저 목록-구조를 초기화 하는 데 사용 하는 예를 들어 하나-식이 아닙니다.  이 문제를 해결 하려면 필요한 초기화를 수행 하는 생성자를 정의 합니다.

다음 예제에서는 C2059를 생성합니다.

```
// C2059b.cpp
// compile with: /c
struct ag_type {
   int a;
   float b;
   // Uncomment the following line to resolve.
   // ag_type(int aa, float bb) : a(aa), b(bb) {}
};

void func(ag_type arg = {5, 7.0});   // C2059
void func(ag_type arg = ag_type(5, 7.0));   // OK
```

잘못 된 형식의 캐스트가 C2059 발생할 수 있습니다.

다음 샘플에서는 C2059를 생성합니다.

```
// C2059c.cpp
// compile with: /clr
using namespace System;
ref class From {};
ref class To : public From {};

int main() {
   From^ refbase = gcnew To();
   To^ refTo = safe_cast<To^>(From^);   // C2059
   To^ refTo2 = safe_cast<To^>(refbase);   // OK
}
```

C2059는 마침표가 포함 된 네임 스페이스 이름을 생성 하려는 경우에 발생할 수 있습니다.

다음 샘플에서는 C2059를 생성합니다.

```
// C2059d.cpp
// compile with: /c
namespace A.B {}   // C2059

// OK
namespace A  {
   namespace B {}
}
```

경우 이름을 정규화 할 수 있는 운영자 C2059 발생할 수 있습니다 (`::`, `->`, 및 `.`) 키워드 야 `template`이 예제에서 보여준 것 처럼:

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::Rebind<X>::Other AX; // error C2059
};
```

기본적으로 C++는 `AY::Rebind`이 템플릿이 아니라고 가정하기 때문에 다음 `<`는 보다 작음 기호로 해석됩니다.  꺾쇠 괄호로 올바르게 구문 분석될 수 있도록 `Rebind`이 템플릿임을 컴파일러에 명시적으로 알려야 합니다. 이 오류를 해결하려면 다음과 같이 종속 형식의 이름에서 `template` 키워드를 사용합니다.

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::template Rebind<X>::Other AX; // correct
};
```
