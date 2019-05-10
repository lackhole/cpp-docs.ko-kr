---
title: 컴파일러 경고 C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: 72700091fcd22271e6913228a1206b3d5efcbdef
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447173"
---
# <a name="compiler-warning-level-4-c4868"></a>컴파일러 경고 (수준 4) C4868

> '_파일_(*line_number*)' 컴파일러는 중괄호로 묶인된 이니셜라이저 목록에서 왼쪽에서 오른쪽 계산 순서를 적용할 수 없습니다.

중괄호로 묶인된 이니셜라이저 목록 요소가 왼쪽에서 오른쪽 순서로 계산 되도록 합니다. 두 가지 경우에 컴파일러는이 순서를 보장할 수 없습니다: 첫 번째 값에서 전달 되는 개체 요소의 일부 경우는 로 컴파일하는 경우 두 번째는 `/clr` 요소 중 일부는 개체의 필드 또는 배열 요소가 있습니다. 컴파일러 왼쪽-오른쪽으로 계산 하지 못할 경우 경고를 C4868 내보냅니다.

Visual Studio 2015 업데이트 2에 대해 수행한 컴파일러 규칙 작업의 결과로이 경고를 생성할 수 있습니다. 이제 Visual Studio 2015 업데이트 2 이전에 컴파일된 코드 C4868를 생성할 수 있습니다.

기본적으로 이 경고는 해제되어 있습니다. 사용 하 여 `/Wall` 이 경고를 활성화 합니다.

이 경고를 해결 하려면 먼저 이니셜라이저 목록 요소의 왼쪽-오른쪽으로 계산 요소의 평가 순서 대로 부작용을 생성할 수 있습니다 때와 같이 필요한 인지 고려 합니다. 대부분의 경우에서 요소가 계산 되는 순서 없는 관찰 가능한 영향입니다.

요소를 전달할 수 있는지 평가 순서는 왼쪽에서 오른쪽 수 있어야 하면 고려해 `const` 대신 참조 합니다. 이 변경 된 다음 코드 샘플에서이 경고를 제거합니다.

## <a name="example"></a>예제

이 샘플 C4868를 생성 하 고를 해결 하는 방법을 보여 줍니다.

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```