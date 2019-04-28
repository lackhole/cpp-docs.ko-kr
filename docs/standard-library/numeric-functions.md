---
title: '&lt;numeric&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- numeric/std::accumulate
- numeric/std::adjacent_difference
- numeric/std::inner_product
- numeric/std::iota
- numeric/std::partial_sum
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
helpviewer_keywords:
- std::accumulate [C++]
- std::adjacent_difference [C++]
- std::inner_product [C++]
- std::iota [C++]
- std::partial_sum [C++]
ms.openlocfilehash: 6df37cf4f6c8afe09f25550d4fc0d9acb553ac52
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236560"
---
# <a name="ltnumericgt-functions"></a>&lt;numeric&gt; 함수

||||
|-|-|-|
|[accumulate](#accumulate)|[adjacent_difference](#adjacent_difference)|[inner_product](#inner_product)|
|[iota](#iota)|[partial_sum](#partial_sum)|

## <a name="accumulate"></a>  accumulate

연속적 부분 합계를 계산하여 일부 초기값을 비롯한 지정된 범위 내 모든 요소의 합계를 계산하거나, 합계 대신 지정된 이진 연산을 사용하여 유사하게 구한 연속적 부분 결과의 결과를 계산합니다.

```cpp
template <class InputIterator, class Type>
Type accumulate(InputIterator first, InputIterator last, Type val);

template <class InputIterator, class Type, class BinaryOperation>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type val,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*first*<br/>
지정된 이진 연산에 따라 합을 계산하거나 결합할 범위의 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

*last*<br/>
반복된 누적에 실제로 포함된 마지막 요소 하나 다음 위치의 지정된 이진 연산에 따라 합을 계산하거나 결합할 범위의 마지막 요소를 주소 지정하는 입력 반복기입니다.

*val*<br/>
지정된 이진 연산에 따라 각 요소가 차례로 추가되거나 결합되는 초기값입니다.

*binary_op*<br/>
지정된 범위의 각 요소와 이전 적용의 결과에 적용할 이진 연산입니다.

### <a name="return-value"></a>반환 값

합한 *val* 및 첫 번째 템플릿 함수의 경우, 두 번째 템플릿 함수를 지정 된 합계 연산 대신 이항 연산에 적용 한 결과 대 한 지정 된 범위의 모든 요소 (  *PartialResult, \*Iter*), 여기서 *PartialResult* 작업의 이전 응용 프로그램의 결과인 및 `Iter` 가 범위에서 요소를 가리키는 반복기입니다.

### <a name="remarks"></a>설명

초기값 것 잘 정의 된 결과 비어 있는 경우 범위, 이때 *val* 반환 됩니다. 이진 연산은 결합 법칙이나 교환 법칙이 성립하지 않아도 됩니다. 결과 초기 값으로 초기화 됩니다 *val* 차례로 *결과*  =  `binary_op` ( *결과*하십시오 <strong>\*</strong> `Iter`) 범위를 통해 반복적으로 계산 되는 `Iter` 은 범위의 연속 요소를 가리키는 반복기입니다. 범위는 유효해야 하며 복잡성은 범위의 크기에 비례해야 합니다. 반복 중에 닫기가 가능하도록 하려면 이진 연산자의 반환 형식을 **Type**으로 변환할 수 있어야 합니다.

### <a name="example"></a>예제

```cpp
// numeric_accum.cpp
// compile with: /EHsc
#include <vector>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2(20);
   vector <int>::iterator iter1, iter2;

   int i;
   for (i = 1; i < 21; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   // The first member function for the accumulated sum
   int total;
   total = accumulate(v1.begin(), v1.end(), 0);

   cout << "The sum of the integers from 1 to 20 is: "
        << total << "." << endl;

   // Constructing a vector of partial sums
   int j = 0, partotal;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      partotal = accumulate(v1.begin(), iter1 + 1, 0);
      v2[j] = partotal;
      j++;
   }

   cout << "The vector of partial sums is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function for the accumulated product
   vector <int> v3, v4(10);
   vector <int>::iterator iter3, iter4;

   int s;
   for (s = 1; s < 11; s++)
   {
      v3.push_back(s);
   }

   cout << "The original vector v3 is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl;

   int ptotal;
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());

   cout << "The product of the integers from 1 to 10 is: "
        << ptotal << "." << endl;

   // Constructing a vector of partial products
   int k = 0, ppartotal;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());
      v4[k] = ppartotal;
      k++;
   }

   cout << "The vector of partial products is:\n ( " ;
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)
      cout << *iter4 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The sum of the integers from 1 to 20 is: 210.
The vector of partial sums is:
( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).

The original vector v3 is:
( 1 2 3 4 5 6 7 8 9 10 ).
The product of the integers from 1 to 10 is: 3628800.
The vector of partial products is:
( 1 2 6 24 120 720 5040 40320 362880 3628800 ).
```

## <a name="adjacent_difference"></a>  adjacent_difference

각 요소와 입력 범위의 해당 선행 작업간 연속 차이를 계산하고 결과를 대상 범위로 출력하거나 차이 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.

```cpp
template <class InputIterator, class OutIterator>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*first*<br/>
입력 범위에서 해당 선행 작업과 차별화해야 하거나 지정된 다른 이진 작업에서 값 쌍을 처리해야 하는 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

*last*<br/>
입력 범위에서 해당 선행 작업과 차별화해야 하거나 지정된 다른 이진 작업에서 값 쌍을 처리해야 하는 마지막 요소를 주소 지정하는 입력 반복기입니다.

*result*<br/>
일련의 차이 또는 지정된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정하는 출력 반복기입니다.

*binary_op*<br/>
차이 절차에서 차감 연산을 대체하는 일반화된 연산에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

대상 범위 끝을 주소 지정하는 출력 반복기:`result` + ( `last` - `first`)

### <a name="remarks"></a>설명

출력 반복기 _ *결과* 입력된 반복기와 동일한 반복기 일 수 * 먼저 * 있도록 `adjacent_difference`s 계산할 수 있습니다.

값의 시퀀스에 대 한 *를*1 *를*2 *를*입력된 범위에서 첫 번째 템플릿 함수에서 3 저장 연속 `partial_difference`s *를*1 *를*2- *는*1, a3- *는*2를 대상 범위입니다.

값의 시퀀스에 대 한 *를*1 *를*2 *를*3, 두 번째 템플릿 함수는 입력된 범위에서 저장 연속 `partial_difference`s *를* 1 *는*2 `binary_op` *는*1 *를*3 `binary_op` *를*대상 범위에서 2.

이항 연산 `binary_op`는 적용 연산 순서가 완전히 적용되므로 결합성이 있거나 가환적일 필요가 없습니다.

### <a name="example"></a>예제

```cpp
// numeric_adj_diff.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend, LIterend2;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t * t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the adjacent_differences of
   // elements in a list output to a vector
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "Output vector containing adjacent_differences is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the adjacent products of the elements in a list
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the adjacent products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of adjacent_differences in place
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="inner_product"></a>  inner_product

두 범위의 요소 전체의 곱의 합을 계산하여 지정된 초기값에 추가하거나 합 및 곱 이진 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차의 결과를 계산합니다.

```cpp
template <class InputIterator1, class InputIterator2, class Type>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val,
    BinaryOperation1  binary_op1,
    BinaryOperation2  binary_op2);
```

### <a name="parameters"></a>매개 변수

*first1*<br/>
두 번째 범위와의 일반화된 내부 곱 또는 내부 곱을 계산할 첫 번째 범위의 첫 번째 요소 주소를 지정하는 입력 반복기입니다.

*last1*<br/>
두 번째 범위와의 일반화된 내부 곱 또는 내부 곱을 계산할 첫 번째 범위의 마지막 번째 요소 주소를 지정하는 입력 반복기입니다.

*first2*<br/>
첫 번째 범위와의 일반화된 내부 곱 또는 내부 곱을 계산할 두 번째 범위의 첫 번째 요소 주소를 지정하는 입력 반복기입니다.

*val*<br/>
범위 간의 내부 곱 또는 일반화된 내부 곱을 더할 초기값입니다.

*binary_op1*<br/>
내부 곱 일반화에서 요소별 곱에 적용되는 합계의 내부 곱 연산을 대체하는 이진 연산입니다.

*binary_op2*<br/>
내부 곱 일반화에서 곱하기의 내부 곱 요소별 연산을 대체하는 이진 연산입니다.

### <a name="return-value"></a>반환 값

첫 번째 구성원 함수는 요소별 곱의 합을 반환하고 해당 합을 지정된 초기값에 더합니다. 따라서 값 *a*i 및 *b*i의 범위에 대해 이 함수는 다음 결과를 반환합니다.

`val` + ( *a*1 \* *b*1 ) + ( *a*2 \* *b*2 ) + ... + ( *a*n \* *b*n )

반복적으로 바꿔 *val* 사용 하 여 `val` + ( *는*있나요 \* *b*i).

두 번째 구성원 함수는 다음 결과를 반환합니다.

`val` *binary_op1* ( *는*1 *binary_op2* *b*1) *binary_op1* ( *를* 2*binary_op2* *b*2) *binary_op1* ... *binary_op1* ( *는*n *binary_op2* *b*n)

반복적으로 바꿔 *val* 사용 하 여 `val` *binary_op1* ( *는*i *binary_op2* *b* i)입니다.

### <a name="remarks"></a>설명

초기 값을 하면 것 잘 정의 된 결과 비어 있는 경우 범위, 이때 *val* 반환 됩니다. 이진 연산은 결합 법칙이나 교환 법칙이 성립하지 않아도 됩니다. 범위는 유효해야 하며 복잡성은 범위의 크기에 비례해야 합니다. 반복 중에 닫기가 가능하도록 하려면 이진 연산자의 반환 형식을 **Type**으로 변환할 수 있어야 합니다.

### <a name="example"></a>예제

```cpp
// numeric_inner_prod.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   vector <int> v1, v2(7), v3(7);
   vector <int>::iterator iter1, iter2, iter3;

   int i;
   for (i = 1; i <= 7; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   list <int> l1, l2(7);
   list <int>::iterator lIter1, lIter2;

   int t;
   for (t = 1; t <= 7; t++)
   {
      l1.push_back(t);
   }

   cout << "The original list l1 is:\n ( " ;
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)
      cout << *lIter1 << " ";
   cout << ")." << endl;

   // The first member function for the inner product
   int inprod;
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);

   cout << "The inner_product of the vector v1 and the list l1 is: "
        << inprod << "." << endl;

   // Constructing a vector of partial inner_products between v1 & l1
   int j = 0, parinprod;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);
      v2[j] = parinprod;
      j++;
   }

   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function used to compute
   // the product of the element-wise sums
   int inprod2;
   inprod2 = inner_product (v1.begin(), v1.end(),
      l1.begin(), 1, multiplies<int>(), plus<int>());

   cout << "The sum of the element-wise products of v1 and l1 is: "
        << inprod2 << "." << endl;

   // Constructing a vector of partial sums of element-wise products
   int k = 0, parinprod2;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      parinprod2 =
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,
         multiplies<int>(), plus<int>());
      v3[k] = parinprod2;
      k++;
   }

   cout << "Vector of partial sums of element-wise products is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl << endl;
}
```

## <a name="iota"></a>  iota

첫 번째 요소를 사용 하 여 시작 하 고 해당 값의 연속적 증분을 사용 하 여 채우기 시작 값을 저장 (` value++`)의 각 간격의 요소에서 `[ first,  last)`합니다.

```cpp
template <class ForwardIterator, class Type>
void iota(ForwardIterator first, ForwardIterator last, Type value);
```

### <a name="parameters"></a>매개 변수

*first*<br/>
채울 범위의 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

*last*<br/>
채울 범위의 마지막 요소를 주소 지정하는 입력 반복기입니다.

*값*<br/>
첫 번째 요소에 저장하고 후속 요소에 대해 연속적으로 증분할 시작 값입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는 [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle) 함수를 사용할 수 있도록 정수 [list](../standard-library/list.md)를 채운 다음 `list`로 [vector](../standard-library/vector.md)를 채우는 `iota` 함수의 몇 가지 사용 방법을 보여 줍니다.

```cpp
// compile by using: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <numeric>
#include <list>
#include <vector>
#include <iostream>

using namespace std;

int main(void)
{
    list <int> intList(10);
    vector <list<int>::iterator> intVec(intList.size());

    // Fill the list
    iota(intList.begin(), intList.end(), 0);

    // Fill the vector with the list so we can shuffle it
    iota(intVec.begin(), intVec.end(), intList.begin());

    random_shuffle(intVec.begin(), intVec.end());

    // Output results
    cout << "Contents of the integer list: " << endl;
    for (auto i: intList) {
        cout << i << ' ';
    }
    cout << endl << endl;

    cout << "Contents of the integer list, shuffled by using a vector: " << endl;
    for (auto i: intVec) {
        cout << *i << ' ';
    }
    cout << endl;
}
```

## <a name="partial_sum"></a>  partial_sum

첫 번째 요소부터 *i*번째 요소까지 입력 범위에서 일련의 합계를 계산하고 각 합계의 결과를 대상 범위의 *i*번째 요소에 저장하거나 합 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.

```cpp
template <class InputIterator, class OutIt>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*first*<br/>
지정된 이진 연산에 따라 부분적으로 합을 계산하거나 결합할 범위의 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

*last*<br/>
반복된 누적에 실제로 포함된 마지막 요소 하나 다음 위치의 지정된 이진 연산에 따라 부분적으로 합을 계산하거나 결합할 범위의 마지막 요소를 주소 지정하는 입력 반복기입니다.

*result*<br/>
일련의 부분적 합 또는 지정된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정하는 출력 반복기입니다.

*binary_op*<br/>
부분적 합 절차에서 합 연산을 대체하는 일반화된 연산에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

대상 범위의 끝을 지정 하는 출력 반복기: `result` + (`last` - `first`),

### <a name="remarks"></a>설명

출력 반복기 *결과* 입력된 반복기와 동일한 반복기 일 수 *첫 번째*준비에서 부분 합계를 계산 될 수 있도록 합니다.

입력 범위의 값 시퀀스 *a*1, *a*2, *a*3에 대해 첫 번째 템플릿 함수는 연속 부분 합을 대상 범위에 저장합니다. 여기서 *i*번째 요소는 (  ( ( *a*1 + *a*2) + *a*3) *a*i)로 지정됩니다.

값의 시퀀스에 대 한 *는*1 *는*2 *는*3 입력된 범위의 두 번째 템플릿 함수는 저장 여기서 i 번째 요소는 대상 범위에서 연속적 부분 합계 지정 된 ((( *를*1 `binary_op` *는*2) `binary_op` *를*3) *를*i).

이항 연산 *binary_op* 결합형 또는 가환 적 될 필요가 없습니다, 작업 순서에 적용 되기 때문에 완전히 지정 합니다.

### <a name="example"></a>예제

```cpp
// numeric_partial_sum.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the partial sums of
   // elements in a list output to a vector
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "The output vector containing the partial sums is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the partial product of the elements in a list
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the partial products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of partial sums in place
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "The in place output partial_sum list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="see-also"></a>참고자료

[\<numeric>](../standard-library/numeric.md)<br/>
