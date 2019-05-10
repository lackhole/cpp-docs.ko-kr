---
title: 컴파일러 경고 (수준 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: 09b6e5b8dc984b35df7de96f5cf8610f2b0f16af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401529"
---
# <a name="compiler-warning-level-3-c4839"></a>컴파일러 경고 (수준 3) C4839

> 클래스의 비표준 사용*형식*' variadic 함수에 인수로 서

와 같이 variadic 함수에 전달 되는 클래스 또는 구조체 `printf` 일반적으로 복사 가능 해야 합니다. 해당 개체를 전달할 때 컴파일러는 비트 복사본을 만들기만 하고 생성자 또는 소멸자를 호출하지 않습니다.

이 경고는 Visual Studio 2017부터 사용할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4839 오류가 생성 됩니다.

```cpp
// C4839.cpp
// compile by using: cl /EHsc /W3 C4839.cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function
}
```

오류를 수정하려면 일반적으로 복사 가능한 형식을 반환하는 멤버 함수를 호출하거나

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

빌드 및 관리를 사용 하 여 문자열 `CStringW`, 제공 된 `operator LPCWSTR()` 캐스트를 사용 해야는 `CStringW` 형식 문자열에 필요한 C 포인터에 대 한 개체입니다.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```