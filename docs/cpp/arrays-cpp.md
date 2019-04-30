---
title: 배열 (C++)
ms.date: 11/19/2018
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
ms.openlocfilehash: 176e358bd0217ac914eb4ee6079126d3f429b6dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184520"
---
# <a name="arrays-c"></a>배열 (C++)

배열은 서로 유사한 개체의 컬렉션입니다. 가장 간단한 배열은 다음과 같은 시퀀스로 선언될 수 있는 벡터입니다.

> *decl-specifier* *identifier* **\[** *constant-expression* **]**<br/>
> *decl-specifier* *identifier* **\[]**<br/>
> *decl-specifier* *identifer* **\[]\[** *constant-expression* **]** . . .<br/>
> *decl-specifier* *identifier* **\[** *constant-expression* **]** **\[** *constant-expression* **]** . . .

1. 선언 지정자:

   - 선택적 저장소 클래스 지정자.

   - 선택적 **상수** 및/또는 **volatile** 지정자입니다.

   - 배열 요소의 형식 이름입니다.

1. 선언자:

   - 식별자입니다.

   - 대괄호로 묶인 정수 계열 형식의 상수 식  **\[]** 합니다. 추가 대괄호를 사용 하 여 여러 차원을 선언 하는 경우 첫 번째 대괄호 집합에서 상수 식을 생략할 수 있습니다.

   - 상수 식을 묶는 선택적 추가 대괄호입니다.

1. 선택적 이니셜라이저입니다. 자세한 내용은 [이니셜라이저](../cpp/initializers.md)합니다.

배열의 요소 수를 지정 하 여는 *상수-식*합니다. 배열의 첫 번째 요소는 0 번째 요소 이며 마지막 요소는 (*n*-1) 요소에 있는 *n* 요소 배열에 포함 될 수입니다. 합니다 *상수-식* 정수 계열 형식 이어야 하며 0 보다 커야 합니다. 크기가 0 인 배열은 배열이의 마지막 필드가 있는 경우에 유효는 **구조체** 하거나 **union** Microsoft 확장 (/Ze)을 사용 하는 경우 및 합니다.

다음 예제에서는 런타임에 배열을 정의하는 방법을 보여 줍니다.

```cpp
// arrays.cpp
// compile with: /EHsc
#include <iostream>

int main() {
   using namespace std;
   int size = 3, i = 0;

   int* myarr = new int[size];

   for (i = 0 ; i < size ; i++)
      myarr[i] = 10;

   for (i = 0 ; i < size ; i++)
      printf_s("myarr[%d] = %d\n", i, myarr[i]);

   delete [] myarr;
}
```

배열은 파생 형식 및 함수에 대 한 참조를 제외 하 고 다른 파생 또는 기본 형식에서 생성할 수 있습니다 하 고 **void**합니다.

다른 배열에서 생성된 배열은 다차원 배열입니다. 이러한 다차원 배열은 여러 개의 대괄호로 묶인 상수 식을 순서대로 배치하여 지정됩니다. 예를 들어 다음 선언을 생각해 볼 수 있습니다.

```cpp
int i2[5][7];
```

형식의 배열을 지정 합니다 **int**, 다음 그림에 표시 된 대로 5 개의 행과 7 개의 열, 2 차원 행렬에 개념적으로 정렬 합니다.

![다중의 개념적 레이아웃&#45;차원 배열인](../cpp/media/vc38rc1.gif "다중의 개념적 레이아웃&#45;차원 배열") <br/>
다차원 배열의 개념적 레이아웃

이니셜라이저 목록이 있는 다차원 배열의 선언에서 (에 설명 된 대로 [이니셜라이저](../cpp/initializers.md)), 첫 번째 차원에 대 한 범위를 지정 하는 상수 식을 생략할 수 있습니다. 예를 들어:

```cpp
// arrays2.cpp
// compile with: /c
const int cMarkets = 4;
// Declare a float that represents the transportation costs.
double TransportCosts[][cMarkets] = {
   { 32.19, 47.29, 31.99, 19.11 },
   { 11.29, 22.49, 33.47, 17.29 },
   { 41.97, 22.09,  9.76, 22.55 }
};
```

앞의 선언은 세 개의 행과 네 개의 열로 구성된 배열을 정의합니다. 행은 공장을 나타내고 열은 공장에서 출하되는 시장을 나타냅니다. 값은 공장에서 시장까지의 운송 비용입니다. 배열의 첫 번째 차원은 생략되었지만 컴파일러가 이니셜라이저를 검사하여 해당 차원을 채웁니다.

이 단원의 항목:

- [배열 사용](../cpp/using-arrays-cpp.md)

- [식의 배열](../cpp/arrays-in-expressions.md)

- [첨자 연산자의 해석](../cpp/interpretation-of-subscript-operator.md)

- [배열 형식에 대한 간접 참조](../cpp/indirection-on-array-types.md)

- [C++ 배열 순서 지정](../cpp/ordering-of-cpp-arrays.md)

## <a name="example"></a>예제

다차원 배열의 첫 번째 차원에 대한 범위 지정을 생략하는 기술은 함수 선언에 다음과 같이 사용할 수도 있습니다.

```cpp
// multidimensional_arrays.cpp
// compile with: /EHsc
// arguments: 3
#include <limits>   // Includes DBL_MAX
#include <iostream>

const int cMkts = 4, cFacts = 2;

// Declare a float that represents the transportation costs
double TransportCosts[][cMkts] = {
   { 32.19, 47.29, 31.99, 19.11 },
   { 11.29, 22.49, 33.47, 17.29 },
   { 41.97, 22.09,  9.76, 22.55 }
};

// Calculate size of unspecified dimension
const int cFactories = sizeof TransportCosts /
                  sizeof( double[cMkts] );

double FindMinToMkt( int Mkt, double myTransportCosts[][cMkts], int mycFacts);

using namespace std;

int main( int argc, char *argv[] ) {
   double MinCost;

   if (argv[1] == 0) {
      cout << "You must specify the number of markets." << endl;
      exit(0);
   }
   MinCost = FindMinToMkt( *argv[1] - '0', TransportCosts, cFacts);
   cout << "The minimum cost to Market " << argv[1] << " is: "
       << MinCost << "\n";
}

double FindMinToMkt(int Mkt, double myTransportCosts[][cMkts], int mycFacts) {
   double MinCost = DBL_MAX;

   for( int i = 0; i < cFacts; ++i )
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?
         MinCost : TransportCosts[i][Mkt];

   return MinCost;
}
```

```Output
The minimum cost to Market 3 is: 17.29
```

## <a name="comments"></a>설명

`FindMinToMkt` 함수는 새 공장을 추가할 때 코드 변경 내용 없이 다시 컴파일하기만 하는 방식으로 작성됩니다.
