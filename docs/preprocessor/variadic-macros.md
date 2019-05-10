---
title: 가변 매크로
ms.date: 11/04/2016
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: da159ef979ccc38845064debebae55356bc9e9bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179571"
---
# <a name="variadic-macros"></a>가변 매크로

가변 매크로 인수의 변수 번호를 포함 하는 함수 형식 매크로입니다.

## <a name="remarks"></a>설명

가변 매크로 사용 하려면 줄임표 매크로 정의에서 대체 식별자 최종 형식 인수로 지정할 있습니다 `__VA_ARGS__` 불필요 한 인수를 삽입할 정의에 사용할 수 있습니다.  `__VA_ARGS__` 쉼표로 구분 하를 포함 하 고 줄임표를 일치 하는 인수의 모든으로 바뀝니다.

C 표준 매크로 후행 쉼표를 사용 하 여 식을 확인 되지 않으면 되도록 줄임표에 하나 이상의 인수를 전달 되어야 합니다를 지정 합니다.  줄임표에 인수 전달 되는 경우 Visual C++ 구현 후행 쉼표를 표시 되지 것입니다.

## <a name="example"></a>예제

```cpp
// variadic_macros.cpp
#include <stdio.h>
#define EMPTY

#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }
#define CHECK3(...) { printf(__VA_ARGS__); }
#define MACRO(s, ...) printf(s, __VA_ARGS__)

int main() {
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print

    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");

    // always invokes printf in the macro
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");

    MACRO("hello, world\n");

    MACRO("error\n", EMPTY); // would cause error C2059, except VC++
                             // suppresses the trailing comma
}
```

```Output
here are some varargs1(1)
here are some varargs2(4)
here are some varargs3(5)
hello, world
error
```

## <a name="see-also"></a>참고자료

[매크로(C/C++)](../preprocessor/macros-c-cpp.md)