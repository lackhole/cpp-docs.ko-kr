---
title: unary_negate 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::unary_negate
helpviewer_keywords:
- unary_negate class
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
ms.openlocfilehash: 96d70a24b87a84275f17813e76473a82fbff90da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399384"
---
# <a name="unarynegate-class"></a>unary_negate 클래스

지정된 단항 함수의 반환 값을 부정하는 멤버 함수를 제공하는 템플릿 클래스입니다. C + + 17 위해에서 사용 되지 않음 [not_fn](functional-functions.md#not_fn)합니다.

## <a name="syntax"></a>구문

```cpp
template <class Predicate>
class unary_negate
    : public unaryFunction<typename Predicate::argument_type, bool>
{
public:
    explicit unary_negate(const Predicate& Func);
    bool operator()(const typename Predicate::argument_type& left) const;
};
```

### <a name="parameters"></a>매개 변수

*Func*<br/>
부정할 단항 함수입니다.

*left*<br/>
부정할 단항 함수의 피연산자입니다.

## <a name="return-value"></a>반환 값

단항 함수의 부정

## <a name="remarks"></a>설명

단항 함수 개체의 복사본을 저장 하는 템플릿 클래스  *\_Func*합니다. 해당 멤버 함수 정의 `operator()` 반환 `!_Func(left)`합니다.

`unary_negate`의 생성자는 직접 사용되는 경우가 거의 없습니다. 도우미 함수 [not1](../standard-library/functional-functions.md#not1)을 사용하면 **unary_negator** 어댑터 조건자를 보다 쉽게 선언하고 사용할 수 있습니다.

## <a name="example"></a>예제

```cpp
// functional_unary_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));

    // The following helper function not1 also works for the above line
    // not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
*/
```

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
