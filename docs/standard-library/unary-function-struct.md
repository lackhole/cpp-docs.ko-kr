---
title: unary_function 구조체
ms.date: 11/04/2016
f1_keywords:
- functional/std::unary
helpviewer_keywords:
- unary_function class
ms.assetid: 04c2fbdc-c1f6-48ed-b6cc-292a6d484627
ms.openlocfilehash: aaca8d48171ebb4043e9c8f0ea66316feb73d39c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399397"
---
# <a name="unaryfunction-struct"></a>unary_function 구조체

단항 함수 개체를 제공하는 파생 클래스에 상속될 수 있는 형식을 정의하는 빈 기본 구조체입니다.

## <a name="syntax"></a>구문

```cpp
struct unary_function
{
   typedef Arg argument_type;
   typedef Result result_type;
};
```

## <a name="remarks"></a>설명

템플릿 구조체는 **result_type**`operator()`(**constargument_type&**) **const** 형식의 구성원 함수를 정의하는 클래스의 기준으로 사용됩니다.

이러한 모든 파생 단항 함수는 유일한 인수 유형을 **argument_type**으로, 반환 형식을 **result_type**로 참조할 수 있습니다.

## <a name="example"></a>예제

```cpp
// functional_unary_function.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan10: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 10);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(), greaterthan10());
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
*/
```

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
