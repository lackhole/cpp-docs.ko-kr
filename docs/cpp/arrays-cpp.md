---
title: 배열 (C++)
ms.date: 11/14/2019
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
ms.openlocfilehash: 91c57a9c4ef190dcace1813dd81739ac72e6b358
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188997"
---
# <a name="arrays-c"></a>배열 (C++)

An array is a sequence of objects of the same type that occupy a contiguous area of memory. Traditional C-style arrays are the source of many bugs, but are still common, especially in older code bases. In modern C++, we strongly recommend using [std::vector](../standard-library/vector-class.md) or [std::array](../standard-library/array-class-stl.md) instead of C-style arrays described in this section. Both of these standard library types store their elements as a contiguous block of memory but provide much greater type safety along with iterators that are guaranteed to point to a valid location within the sequence. For more information, see [Containers (Modern C++)](containers-modern-cpp.md).

## <a name="stack-declarations"></a>Stack declarations

In a C++ array declaration, the array size is specified after the variable name, not after the type name as in some other languages. The following example declares an array of 1000 doubles to be allocated on the stack. The number of elements must be supplied as an integer literal or else as a constant expression because the compiler has to know how much stack space to allocate; it cannot use a value computed at run-time. Each element in the array is assigned a default value of 0. If you do not assign a default value, each element will initially contain whatever random values happen to be at that location.

```cpp
    constexpr size_t size = 1000;

    // Declare an array of doubles to be allocated on the stack
    double numbers[size] {0};

    // Assign a new value to the first element
    numbers[0] = 1;

    // Assign a value to each subsequent element
    // (numbers[1] is the second element in the array.)
    for (size_t i = 1; i < size; i++)
    {
        numbers[i] = numbers[i-1] * 1.1;
    }

    // Access each element
    for (size_t i = 0; i < size; i++)
    {
        std::cout << numbers[i] << " ";
    }
```

The first element in the array is the 0th element, and the last element is the (*n*-1) element, where *n* is the number of elements the array can contain. The number of elements in the declaration must be of an integral type and must be greater than 0. It is your responsibility to ensure that your program never passes a value to the subscript operator that is greater than `(size - 1)`.

A zero-sized array is legal only when the array is the last field in a **struct** or **union** and when the Microsoft extensions (/Ze) are enabled.

Stack-based arrays are faster to allocate and access than heap-based arrays, but the number of elements can't be so large that it uses up too much stack memory. How much is too much depends on your program. You can use profiling tools to determine whether an array is too large.

## <a name="heap-declarations"></a>Heap declarations

If you require an array that is too large to be allocated on the stack, or whose size cannot be known at compile time, you can allocate it on the heap with a [new\[\]](new-operator-cpp.md) expression. The operator returns a pointer to the first element. You can use the subscript operator with the pointer variable just as with a stack-based array. You can also use [pointer arithmetic](../c-language/pointer-arithmetic.md) to move the pointer to any arbitrary elements in the array. It is your responsibility to ensure that:

- you always keep a copy of the original pointer address so that you can delete the memory when you no longer need the array.
- you do not increment or decrement the pointer address past the array bounds.

The following example shows how to define an array on the heap at run time, and how to access the array elements using the subscript operator or by using pointer arithmetic:

```cpp

void do_something(size_t size)
{
    // Declare an array of doubles to be allocated on the heap
    double* numbers = new double[size]{ 0 };

    // Assign a new value to the first element
    numbers[0] = 1;

    // Assign a value to each subsequent element
    // (numbers[1] is the second element in the array.)
    for (size_t i = 1; i < size; i++)
    {
        numbers[i] = numbers[i - 1] * 1.1;
    }

    // Access each element with subscript operator
    for (size_t i = 0; i < size; i++)
    {
        std::cout << numbers[i] << " ";
    }

    // Access each element with pointer arithmetic
    // Use a copy of the pointer for iterating
    double* p = numbers;

    for (size_t i = 0; i < size; i++)
    {
        // Dereference the pointer, then increment it
        std::cout << *p++ << " ";
    }

    // Alternate method:
    // Reset p to numbers[0]:
    p = numbers;

    // Use address of pointer to compute bounds.
    // The compiler computes size as the number
    // of elements * (bytes per element).
    while (p < (numbers + size))
    {
        // Dereference the pointer, then increment it
        std::cout << *p++ << " ";
    }

    delete[] numbers; // don't forget to do this!

}
int main()
{
    do_something(108);
}

```

## <a name="initializing-arrays"></a>배열 초기화

You can initialize an array in a loop, one element at a time, or in a single statement. The contents of the following two arrays are identical:

```cpp
    int a[10];
    for (int i = 0; i < 10; ++i)
    {
        a[i] = i + 1;
    }

    int b[10]{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
```

## <a name="passing-arrays-to-functions"></a>Passing arrays to functions

When an array is passed to a function, it is passed as a pointer to the first element. This is true for both stack-based and heap-based arrays. The pointer contains no additional size or type information. This behavior is called *pointer decay*. When you pass an array to a function, you must always specify the number of elements in a separate parameter. This behavior also implies that the array elements are not copied when the array is passed to a function. To prevent the function from modifying the elements, specify the parameter as a pointer to **const** elements.

The following example shows a function that accepts an array and a length. The pointer points to the original array, not a copy. Because the parameter is not **const**, the function can modify the array elements.

```cpp
void process(double p*, const size_t len)
{
    std::cout << "process:\n";
    for (size_t i = 0; i < len; ++i)
    {
        // do something with p[i]
    }
}
```

Declare the array as const to make it read-only within the function block:

```cpp
void process(const double p*, const size_t len);
```

The same function can also be declared in these ways, with no change in behavior. The array is still passed as a pointer to the first element:

```cpp
// Unsized array
void process(const double p[] const size_t len);

// Fixed-size array. Length must still be specified explicitly.
void process(const double p[1000], const size_t len);
```

## <a name="multidimensional-arrays"></a>Multidimensional arrays

다른 배열에서 생성된 배열은 다차원 배열입니다. 이러한 다차원 배열은 여러 개의 대괄호로 묶인 상수 식을 순서대로 배치하여 지정됩니다. 예를 들어 다음 선언을 생각해 볼 수 있습니다.

```cpp
int i2[5][7];
```

It specifies an array of type **int**, conceptually arranged in a two-dimensional matrix of five rows and seven columns, as shown in the following figure:

![Conceptual layout of a multi&#45;dimensional array](../cpp/media/vc38rc1.gif "Conceptual layout of a multi&#45;dimensional array") <br/>
다차원 배열의 개념적 레이아웃

In declarations of multidimensioned arrays that have an initializer list (as described in [Initializers](../cpp/initializers.md)), the constant expression that specifies the bounds for the first dimension can be omitted. 예를 들어 다음과 같은 가치를 제공해야 합니다.

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

Use of the indirection operator (*) on an n-dimensional array type yields an n-1 dimensional array. If n is 1, a scalar (or array element) is yielded.

C++ 배열은 행 중심 순서로 저장됩니다. 행 중심 순서는 마지막 첨자가 가장 빠르게 변경됨을 의미합니다.

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

   for( size_t i = 0; i < cFacts; ++i )
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?
         MinCost : TransportCosts[i][Mkt];

   return MinCost;
}
```

```Output
The minimum cost to Market 3 is: 17.29
```

`FindMinToMkt` 함수는 새 공장을 추가할 때 코드 변경 내용 없이 다시 컴파일하기만 하는 방식으로 작성됩니다.

## <a name="initializing-arrays"></a>배열 초기화

클래스에 생성자가 있으면 해당 클래스의 배열은 생성자에 의해 초기화됩니다. 이니셜라이저 목록의 항목 수가 배열의 요소 수보다 적은 경우 나머지 요소에 대해 기본 생성자가 사용됩니다. 클래스에 정의된 기본 생성자가 없는 경우 이니셜라이저 목록이 완전해야 합니다. 즉, 배열의 각 요소에 하나의 이니셜라이저가 있어야 합니다.

생성자 두 개를 정의하는 `Point` 클래스를 살펴보세요.

```cpp
// initializing_arrays1.cpp
class Point
{
public:
   Point()   // Default constructor.
   {
   }
   Point( int, int )   // Construct from two ints
   {
   }
};

// An array of Point objects can be declared as follows:
Point aPoint[3] = {
   Point( 3, 3 )     // Use int, int constructor.
};

int main()
{
}
```

`aPoint`의 첫 번째 요소는 `Point( int, int )` 생성자를 사용하여 생성되고 나머지 두 요소는 기본 생성자를 사용하여 생성됩니다.

Static member arrays (whether **const** or not) can be initialized in their definitions (outside the class declaration). 예를 들어 다음과 같은 가치를 제공해야 합니다.

```cpp
// initializing_arrays2.cpp
class WindowColors
{
public:
    static const char *rgszWindowPartList[7];
};

const char *WindowColors::rgszWindowPartList[7] = {
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };
int main()
{
}
```

## <a name="accessing-array-elements"></a>Accessing array elements

배열 첨자 연산자(`[ ]`)를 사용하여 배열의 개별 요소에 액세스할 수 있습니다. 식에서 아래 첨자 없이 1차원 배열이 사용된 경우 배열 이름은 배열의 첫 번째 요소에 대한 포인터로 평가됩니다.

```cpp
// using_arrays.cpp
int main() {
   char chArray[10];
   char *pch = chArray;   // Evaluates to a pointer to the first element.
   char   ch = chArray[0];   // Evaluates to the value of the first element.
   ch = chArray[3];   // Evaluates to the value of the fourth element.
}
```

다차원 배열을 사용할 때 식에서 다양한 조합을 사용할 수 있습니다.

```cpp
// using_arrays_2.cpp
// compile with: /EHsc /W1
#include <iostream>
using namespace std;
int main() {
   double multi[4][4][3];   // Declare the array.
   double (*p2multi)[3];
   double (*p1multi);

   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.
   p2multi = multi[3];               // Make p2multi point to
                                     // fourth "plane" of multi.
   p1multi = multi[3][2];            // Make p1multi point to
                                     // fourth plane, third row
                                     // of multi.
}
```

In the preceding code, `multi` is a three-dimensional array of type **double**. The `p2multi` pointer points to an array of type **double** of size three. 이 예제에서 배열은 한 개, 두 개 및 세 개의 아래 첨자와 함께 사용됩니다. `cout` 문에서처럼 모든 첨자를 지정하는 것이 더 일반적이기는 하지만 `cout` 문에서처럼 배열 요소의 특정 하위 집합을 선택하는 것이 유용할 때도 있습니다.

## <a name="overloading-subscript-operator"></a>Overloading subscript operator

Like other operators, the subscript operator (`[]`) can be redefined by the user. 첨자 연산자의 기본 동작은 다음 메서드를 사용하여 배열 이름과 첨자를 결합하는 것입니다.

`*((array_name) + (subscript))`

포인터 형식을 비롯한 모든 추가에서와 마찬가지로 형식 크기를 조정하기 위해 크기 조정이 자동으로 수행됩니다. Therefore, the resultant value is not *n* bytes from the origin of array-name; rather, it is the *n*th element of the array. For more information about this conversion, see [Additive operators](additive-operators-plus-and.md).

다차원 배열에서도 다음 메서드를 사용하여 주소가 파생됩니다.

`((array_name) + (subscript1 * max2 * max3 * ... * maxn) + (subscript2 * max3 * ... * maxn) + ... + subscriptn))`

## <a name="arrays-in-expressions"></a>식의 배열

배열 형식의 식별자가 `sizeof`, address-of(`&`) 또는 참조의 초기화 이외의 식에 나타나는 경우 첫 번째 배열 요소에 대한 포인터로 변환됩니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

`psz` 포인터는 `szError1` 배열의 첫 번째 요소를 가리킵니다. Arrays, unlike pointers, are not modifiable l-values. 따라서 다음 대입은 올바르지 않습니다.

```cpp
szError1 = psz;
```

## <a name="see-also"></a>참조

[std::array](../standard-library/array-class-stl.md)
