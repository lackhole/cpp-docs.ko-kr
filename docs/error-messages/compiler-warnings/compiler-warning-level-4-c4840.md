---
title: 컴파일러 경고 (수준 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: a757004659c1a9d2ce858cfae5ddfbc6c024d782
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360010"
---
# <a name="compiler-warning-level-4-c4840"></a>컴파일러 경고 (수준 4) C4840

> 클래스의 비 휴대용 활용*형식*' variadic 함수에 인수로 서

## <a name="remarks"></a>설명

Variadic 함수에 전달 되는 클래스 또는 구조체는 일반적으로 복사 가능 해야 합니다. 해당 개체를 전달할 때 컴파일러는 비트 복사본을 만들기만 하고 생성자 또는 소멸자를 호출하지 않습니다.

이 경고는 Visual Studio 2017부터 사용할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C4840 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

빌드 및 사용 하 여 관리 되는 문자열에 대 한 `CStringW`에 제공 된 `operator LPCWSTR()` 캐스트를 사용 해야는 `CStringW` 형식 문자열에 필요한 C 스타일 문자열 포인터에 대 한 개체:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```