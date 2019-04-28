---
title: 생성자 없이 클래스 및 구조체 초기화(C++)
ms.date: 10/17/2018
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: 4f696f4fc8862b953e40a03c96b88d1a0b7f720b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183416"
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>생성자 없이 클래스 및 구조체 초기화(C++)

클래스, 특히 비교적 간단한 클래스에 대해 항상 생성자를 정의할 필요는 없습니다. 사용자는 다음 예제와 같이 균일 초기화를 사용하여 클래스 또는 구조체의 개체를 초기화할 수 있습니다.

```cpp
// no_constructor.cpp
// Compile with: cl /EHsc no_constructor.cpp
#include <time.h>

// No constructor
struct TempData
{
    int StationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

// Has a constructor
struct TempData2
{
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :
       stationId{id}, timeSet{t}, current{cur}, maxTemp{maximum}, minTemp{minimum} {}
    int stationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

int main()
{
    time_t time_to_set;

    // Member initialization (in order of declaration):
    TempData td{ 45978, time(&time_to_set), 28.9, 37.0, 16.7 };

    // Default initialization = {0,0,0,0,0}
    TempData td_default{};

    // Uninitialized = if used, emits warning C4700 uninitialized local variable
    TempData td_noInit;

    // Member declaration (in order of ctor parameters)
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, time(&time_to_set) };

    return 0;
}
```

클래스 또는 구조체에 생성자가 없는 경우 제공하는 멤버 클래스에서 선언되는 순서로 목록 요소를 참고합니다. 클래스에 생성자가 있는 경우 매개 변수를 순서대로 요소를 제공합니다.

## <a name="see-also"></a>참고 항목

[클래스 및 구조체(C++)](../cpp/classes-and-structs-cpp.md)<br/>
[생성자(C++)](../cpp/constructors-cpp.md)
