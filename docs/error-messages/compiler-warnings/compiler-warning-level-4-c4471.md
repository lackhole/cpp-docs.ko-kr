---
title: 컴파일러 경고 (수준 4) C4471
ms.date: 04/24/2017
f1_keywords:
- C4471
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
ms.openlocfilehash: 0345b730b8fc37329f632bb5d8486c67efd8e3b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400788"
---
# <a name="compiler-warning-level-4-c4471"></a>컴파일러 경고 (수준 4) C4471

'*열거형*': 범위가 지정 되지 않은 열거형의 정방향 선언에는 기본 형식 (int로 가정) 있어야 합니다.

기본 형식에 대 한 범위가 지정 되지 않은 열거형의 정방향 선언 지정 자가 없는 찾았습니다. 기본적으로 시각적 개체 C++ 가정 `int` 열거형의 기본 형식입니다. 다른 형식을 사용 하는 경우 열거형 정의에서 예를 들어 다른 명시적 종류를 지정 하는 경우 또는 다른 형식 이니셜라이저를 암시적으로 설정 된 경우이 문제가 발생할 수 있습니다. 이식성 문제; 할 수도 있습니다. 다른 컴파일러 가정 하지 마십시오 `int` 열거형의 기본 형식입니다.

이 경고는 기본적으로 해제 되어 /Wall 또는 /w 사용할 수 있습니다*N*4471를 명령줄에서 사용 하도록 설정 하거나 #pragma 사용 [경고](../../preprocessor/warning.md) 소스 파일에 있습니다.

일부 경우에이 경고는 의사입니다. 열거형에 대 한 정방향 선언을 정의 뒤에 나오면,이 경고를 발생 시킬 수 있습니다. 예를 들어, 다음이 코드는 C4471 못할 경우에 유효한.

```cpp
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```

## <a name="example"></a>예제

일반적으로 범위가 지정 되지 않은 열거형의 정방향 선언 하는 대신 전체 정의 사용 하려면 안전 합니다. 헤더 파일에 정의 저장 하 고 참조 하는 소스 파일에 포함할 수 있습니다. C++98 이상용으로 작성 된 코드에서 작동 합니다. 이 솔루션을 이식성 및 유지 관리 편의성을 사용 하는 것이 좋습니다.

```cpp
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```

## <a name="example"></a>예제

C + + 11에서 정방향 선언 하는 범위가 지정 되지 않은 열거형에 명시적 형식을 추가할 수 있습니다. Complex 헤더 포함 논리에 대 한 정방향 선언 하는 대신 정의 사용할 수 없습니다 하는 경우에이 솔루션을 권장 합니다. 이 솔루션을 유지 관리 문제가 발생할 수 있습니다: 열거형 정의에 사용 되는 기본 형식을 변경 하면 모든 일치 하는 정방향 선언이 변경 해야 합니다 또는 코드에서 자동 오류가 있을 수 있습니다. 이 문제를 최소화 하기 위해 헤더 파일로 정방향 선언에 넣을 수 있습니다.

```cpp
// C4471c.cpp
// Client code for enumeration defined in C4471d.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example;    // C4471, int assumed
// To fix, replace the lines above with the forward declarations:
// enum Example : unsigned;
// ...
```

```cpp
// C4471d.cpp
// Definition for enumeration used in C4471c.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example : unsigned { item = 0x80000000 }; // explicit type
// ...
```

열거형에 대 한 명시적 형식을 지정 하면, 또한 경고를 사용 하는 것이 좋습니다 [C4369](compiler-warning-level-1-C4369.md), 기본적으로 켜져 있는 합니다. 이 경우 열거형 항목 명시적으로 지정 된 형식과 다른 형식이 필요로 하는 위치를 식별 합니다.

## <a name="example"></a>예제

범위가 지정 된 열거형, C + + 11의 새로운 기능을 사용 하도록 코드를 변경할 수 있습니다. 정 및 열거형을 사용 하는 클라이언트 코드는 범위가 지정 된 열거형을 사용 하도록 변경 되어야 합니다. 사용할 범위가 지정 된 열거형을 네임 스페이스 공해 문제가 있는 경우 정의 된 열거형 항목 이름에는 열거형의 범위로 제한 하는 것이 좋습니다. 범위가 지정 된 열거형의 다른 기능은 다른 정수 계열 또는 열거형 형식으로 사소한 버그의 원인이 될 수 있는 해당 멤버를 암시적으로 변환할 수 없습니다는입니다.

```cpp
// C4471e.cpp
// Client code for scoped enumeration defined in C4471f.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum Example;    // C4471
// To fix, replace the line above with the forward declaration:
// enum class Example;
// ...
```

```cpp
// C4471f.cpp
// Definition for scoped enumeration used in C4471e.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum class Example { item = 0 };
// ...
```

