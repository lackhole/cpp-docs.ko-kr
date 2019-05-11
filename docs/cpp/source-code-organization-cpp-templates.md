---
title: 소스 코드 조직 (C++ 템플릿)
ms.date: 11/04/2016
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
ms.openlocfilehash: 592f17c08b9d4de0f67f17c60521d6e9a11dfc3a
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222007"
---
# <a name="source-code-organization-c-templates"></a>소스 코드 조직 (C++ 템플릿)

클래스 템플릿을 정의 하는 경우이 필요할 때 멤버 정의 컴파일러에 표시 되는 방식으로 소스 코드를 구성 해야 합니다.   사용 하 여 선택할 수 있습니다 합니다 *포함할 모델* 또는 *명시적 인스턴스화* 모델입니다. 포함 모델에서는 템플릿을 사용 하는 모든 파일의 멤버 정의 포함할 수 있습니다. 이 접근 방식을 가장 간단 하 고 구체적인 유형의 템플릿을 사용 하 여 최대 유연성을 제공 합니다. 해당 단점은 컴파일 시간을 늘릴 수 있는 것입니다. 자체 포함 된 파일은 대용량 되거나 영향 경우 프로젝트에 중요 될 수 있습니다. 명시적 인스턴스화 방식의 경우 템플릿 자체는 구체적인 클래스 또는 특정 유형에 대 한 클래스 멤버를 인스턴스화합니다.  이 이렇게 컴파일 시간 속도 높일 수 있지만 템플릿 구현 자가 미리 설정한 클래스만 사용량을 제한 합니다. 일반적으로 컴파일 시간에 문제가 경우가 아니면 포함 모델을 사용 하는 것이 좋습니다.

## <a name="background"></a>배경

템플릿은 컴파일러는 템플릿 또는 해당 멤버 중 하나에 대 한 개체 코드를 생성 하지 않습니다 점에서 일반 클래스와 마찬가지로 않습니다. 구체적인 형식을 사용 하 여 템플릿이 인스턴스화될 때까지 생성 개체가 없습니다. 발견할 경우에 컴파일러는 템플릿 인스턴스화에 같은 `MyClass<int> mc;` 서명이 없는 클래스가 있습니다. 아직 새 클래스를 생성 합니다. 또한 사용 되는 모든 멤버 함수에 대 한 코드를 생성 하려고 합니다. 이러한 정의 하지 않은 파일이 있는 경우 #included 직접 또는 간접적으로 컴파일 중인.cpp 파일에서 컴파일러 내용을 볼 수 없습니다.  컴파일러의 관점에서 반드시 오류가 있으므로 다른 변환 단위에 있는 경우 링커는 찾을 함수를 정의할 수 있습니다.  발생 링커는 코드를 찾을 수 없는 경우는 **확인할 수 없는 외부** 오류입니다.

## <a name="the-inclusion-model"></a>포함 모델

템플릿 정의 변환 단위 전체에 걸쳐 표시 되도록 간단 하 고 가장 일반적인 방법은 자체의 헤더 파일에 정의 추가할 것입니다.  템플릿을 사용 하는 모든.cpp 파일 단순히에 #include 헤더입니다. 이 방법은 표준 라이브러리에서 사용 합니다.

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   }
};
#endif
```

이 방법을 사용 하 여 컴파일러는 완전 한 템플릿 정의에 대 한 액세스 권한이 하 고 템플릿 주문형으로 모든 형식에 대 한를 인스턴스화할 수 있습니다. 것이 간단 하 고 비교적 쉽게 유지 관리할 수 있습니다. 그러나 포함 모델에는 컴파일 시간 측면에서 비용입니다.   이 비용은 큰 프로그램에서 중요할 수 있습니다 다음 경우에 특히 자체 템플릿 헤더 #includes 다른 헤더입니다. 모든.cpp 파일을 #includes 헤더 함수 템플릿 및 모든 정의의 자체 복사본을 받습니다. 링커는 일반적으로 있습니다 끝나지 않는 함수에 대 한 여러 정의 사용 하 여이 작업을 수행 하는 데는 시간이 있도록 항목을 정렬할 수 없습니다. 더 작은 프로그램에서 해당 추가 컴파일 시간이 중요 없는 것입니다.

## <a name="the-explicit-instantiation-model"></a>명시적 인스턴스화 모델

포함 모델 프로젝트에 대 한 실행 가능한 이며 템플릿을 인스턴스화할 하는 데 사용할 수 있는 형식 집합을 명확 하 게 알고,.h 및.cpp 파일을에 템플릿 코드를 분리 및.cpp 파일에서 명시적으로 템플릿을 인스턴스화할 수 있습니다. 이렇게 하면 개체 코드를 생성할 사용자 인스턴스화를 발견할 경우 컴파일러는 참조 하세요.

명시적 인스턴스화를 인스턴스화하 려 엔터티의 서명 뒤에 키워드 템플릿을 사용 하 여 만듭니다. 이 형식 또는 멤버 수 있습니다. 형식으로 명시적으로 인스턴스화하는 경우 모든 멤버가 인스턴스화됩니다.

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for(const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

이전 예제에서는 명시적 인스턴스화.cpp 파일의 맨 아래에 있습니다. A `MyArray` 에 대해서만 사용할 수 있습니다 **이중** 또는 `String` 형식입니다.

> [!NOTE]
> C + + 11에서 합니다 **내보내기** 키워드 템플릿 정의의 컨텍스트에서 사용 되지 않습니다. 실제로이 거의 영향을 주지 하므로 대부분의 컴파일러에서는 것도 지원 되지 않습니다.