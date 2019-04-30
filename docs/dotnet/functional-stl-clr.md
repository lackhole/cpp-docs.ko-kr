---
title: functional(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/functional>
- cliext::binary_delegate
- cliext::binary_delegate_noreturn
- cliext::binary_negate
- cliext::bind1st
- cliext::bind2nd
- cliext::binder1st
- cliext::binder2nd
- cliext::divides
- cliext::equal_to
- cliext::greater
- cliext::greater_equal
- cliext::less
- cliext::less_equal
- cliext::logical_and
- cliext::logical_not
- cliext::logical_or
- cliext::minus
- cliext::modulus
- cliext::multiplies
- cliext::negate
- cliext::not_equal_to
- cliext::not1
- cliext::not2
- cliext::plus
- cliext::unary_delegate
- cliext::unary_delegate_noreturn
- cliext::unary_negate
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
- binary_delegate function [STL/CLR]
- binary_delegate_noreturn function [STL/CLR]
- binary_negate function [STL/CLR]
- bind1st function [STL/CLR]
- bind2nd function [STL/CLR]
- binder1st function [STL/CLR]
- binder2nd function [STL/CLR]
- divides function [STL/CLR]
- equal_to function [STL/CLR]
- greater function [STL/CLR]
- greater_equal function [STL/CLR]
- less function [STL/CLR]
- less_equal function [STL/CLR]
- logical_and function [STL/CLR]
- logical_not function [STL/CLR]
- logical_or function [STL/CLR]
- minus function [STL/CLR]
- modulus function [STL/CLR]
- multiplies function [STL/CLR]
- negate function [STL/CLR]
- not_equal_to function [STL/CLR]
- not1 function [STL/CLR]
- not2 function [STL/CLR]
- plus function [STL/CLR]
- unary_delegate function [STL/CLR]
- unary_delegate_noreturn function [STL/CLR]
- unary_negate function [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
ms.openlocfilehash: f4a99ea972c6d2ea9b9721664cc75dec257fd7b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393755"
---
# <a name="functional-stlclr"></a>functional(STL/CLR)

STL/CLR 헤더를 포함 `<cliext/functional>` 정의 하는 다양 한 템플릿 클래스 및 관련된 템플릿은 대리자 함수입니다.

## <a name="syntax"></a>구문

```
#include <functional>
```

## <a name="requirements"></a>요구 사항

**헤더:** \<cliext/기능 >

**Namespace:** cliext

## <a name="declarations"></a>선언

|대리자|설명|
|--------------|-----------------|
|[binary_delegate(STL/CLR)](#binary_delegate)|두 인수 대리자입니다.|
|[binary_delegate_noreturn(STL/CLR)](#binary_delegate_noreturn)|두 인수 대리자 반환 **void**합니다.|
|[unary_delegate(STL/CLR)](#unary_delegate)|단일 인수 대리자입니다.|
|[unary_delegate_noreturn(STL/CLR)](#unary_delegate_noreturn)|반환 되는 단일 인수 대리자 **void**합니다.|

|클래스|설명|
|-----------|-----------------|
|[binary_negate(STL/CLR)](#binary_negate)|인수가 두 개인 함수인 부정할 함수입니다.|
|[binder1st(STL/CLR)](#binder1st)|첫 번째 인수는 두 인수 함수인 바인딩할 함수입니다.|
|[binder2nd(STL/CLR)](#binder2nd)|두 번째 인수는 두 인수 함수인 바인딩할 함수입니다.|
|[divides(STL/CLR)](#divides)|함수를 나눕니다.|
|[equal_to(STL/CLR)](#equal_to)|같음 비교 함수입니다.|
|[greater(STL/CLR)](#greater)|큰 비교 함수입니다.|
|[greater_equal(STL/CLR)](#greater_equal)|Greater 또는 equal 비교 함수입니다.|
|[less(STL/CLR)](#less)|Less 비교 함수입니다.|
|[less_equal(STL/CLR)](#less_equal)|작거나 같음 비교 함수입니다.|
|[logical_and(STL/CLR)](#logical_and)|논리 AND 함수입니다.|
|[logical_not(STL/CLR)](#logical_not)|논리 함수 없습니다.|
|[logical_or(STL/CLR)](#logical_or)|논리 OR 함수입니다.|
|[minus(STL/CLR)](#minus)|함수를 뺍니다.|
|[modulus(STL/CLR)](#modulus)|모듈러스 함수입니다.|
|[multiplies(STL/CLR)](#multiplies)|곱하기 함수입니다.|
|[negate(STL/CLR)](#negate)|부정 해당 인수를 반환 하는 함수입니다.|
|[not_equal_to(STL/CLR)](#not_equal_to)|같지 않음 비교 함수입니다.|
|[plus(STL/CLR)](#plus)|함수를 추가 합니다.|
|[unary_negate(STL/CLR)](#unary_negate)|단일 인수 함수를 부정 하는 함수입니다.|

|함수|설명|
|--------------|-----------------|
|[bind1st(STL/CLR)](#bind1st)|인수 및 함수 binder1st를 생성합니다.|
|[bind2nd(STL/CLR)](#bind2nd)|인수 및 함수 binder2nd를 생성합니다.|
|[not1(STL/CLR)](#not1)|함수에 대 한 unary_negate를 생성합니다.|
|[not2(STL/CLR)](#not2)|함수에 대 한 binary_negate를 생성합니다.|

## <a name="members"></a>멤버

## <a name="binary_delegate"></a> binary_delegate (STL/CLR)

Genereic 클래스에는 두 인수 대리자를 설명합니다. 사용 하 여 해당 인수 및 반환 형식 기준으로 대리자를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
generic<typename Arg1,
    typename Arg2,
    typename Result>
    delegate Result binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>매개 변수

*Arg1*<br/>
첫 번째 인수의 형식입니다.

*Arg2*<br/>
두 번째 인수의 형식입니다.

*결과*<br/>
반환 형식입니다.

### <a name="remarks"></a>설명

Genereic 대리자는 두 인수 함수를 설명합니다.

note:

`binary_delegate<int, int, int> Fun1;`

`binary_delegate<int, int, int> Fun2;`

형식을 `Fun1` 고 `Fun2` 은 동의어 이며에 대 한 동안:

`delegate int Fun1(int, int);`

`delegate int Fun2(int, int);`

동일한 형식 하지 않습니다.

### <a name="example"></a>예제

```cpp
// cliext_binary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

bool key_compare(wchar_t left, wchar_t right)
    {
    return (left < right);
    }

typedef cliext::binary_delegate<wchar_t, wchar_t, bool> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="binary_delegate_noreturn"></a> binary_delegate_noreturn (STL/CLR)

Genereic 클래스를 반환 하는 두 인수 대리자 설명 **void**합니다. 사용 하 여 해당 인수를 기준으로 대리자를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
generic<typename Arg1,
    typename Arg2>
    delegate void binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>매개 변수

*Arg1*<br/>
첫 번째 인수의 형식입니다.

*Arg2*<br/>
두 번째 인수의 형식입니다.

### <a name="remarks"></a>설명

Genereic 대리자에 반환 하는 두 인수 함수에 설명 **void**합니다.

note:

`binary_delegate_noreturn<int, int> Fun1;`

`binary_delegate_noreturn<int, int> Fun2;`

형식을 `Fun1` 고 `Fun2` 은 동의어 이며에 대 한 동안:

`delegate void Fun1(int, int);`

`delegate void Fun2(int, int);`

동일한 형식 하지 않습니다.

### <a name="example"></a>예제

```cpp
// cliext_binary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void key_compare(wchar_t left, wchar_t right)
    {
    System::Console::WriteLine("compare({0}, {1}) = {2}",
        left, right, left < right);
    }

typedef cliext::binary_delegate_noreturn<wchar_t, wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    kcomp(L'a', L'a');
    kcomp(L'a', L'b');
    kcomp(L'b', L'a');
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(a, a) = False
compare(a, b) = True
compare(b, a) = False
```

## <a name="binary_negate"></a> binary_negate (STL/CLR)

템플릿 클래스를 설명 하는 함수인은 호출 된 경우 반환 논리 구조으로 저장된 하는 두 인수 함수는 아닙니다. 사용 하 여 해당 저장된 함수를 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Fun>
    ref class binary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    explicit binary_negate(Fun% functor);
    binary_negate(binary_negate<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Fun*<br/>
형식 저장된 함수입니다.

## <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|
|stored_function_type|함수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|binary_negate|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|operator delegate_type^()|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 다른 두 인수 함수를 저장 하는 두 인수 함수를 설명 합니다. 멤버 연산자 정의 `operator()` 논리적 반환 개체 함수로 호출 되 면 있도록 두 개의 인수를 사용 하 여 호출 저장된 함수는 아닙니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_binary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="bind1st"></a> bind1st (STL/CLR)

생성 된 `binder1st` 인수 및 함수.

### <a name="syntax"></a>구문

```cpp
template<typename Fun,
    typename Arg>
    binder1st<Fun> bind1st(Fun% functor,
        Arg left);
```

#### <a name="template-parameters"></a>템플릿 매개 변수

*Arg*<br/>
인수 형식입니다.

*Fun*<br/>
함수의 형식입니다.

#### <a name="function-parameters"></a>함수 매개 변수

*functor*<br/>
래핑할 함수입니다.

*left*<br/>
래핑할 첫 번째 인수입니다.

### <a name="remarks"></a>설명

템플릿 함수 [binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)`<Fun>(functor, left)`합니다. 두 번째 인수를 사용 하 여 호출 하는 단일 인수 함수에서 인수가 두 개인 함수 및 첫 번째 인수를 래핑하는 편리한 방법으로 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_bind1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="bind2nd"></a> bind2nd (STL/CLR)

생성 된 `binder2nd` 인수 및 함수.

### <a name="syntax"></a>구문

```cpp
template<typename Fun,
    typename Arg>
    binder2nd<Fun> bind2nd(Fun% functor,
        Arg right);
```

#### <a name="template-parameters"></a>템플릿 매개 변수

*Arg*<br/>
인수 형식입니다.

*Fun*<br/>
함수의 형식입니다.

#### <a name="function-parameters"></a>함수 매개 변수

*functor*<br/>
래핑할 함수입니다.

*right*<br/>
래핑할 두 번째 인수입니다.

### <a name="remarks"></a>설명

템플릿 함수 [binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)`<Fun>(functor, right)`합니다. 첫 번째 인수를 사용 하 여 호출 하는 단일 인수 함수에서 인수가 두 개인 함수 및 두 번째 인수를 래핑하는 편리한 방법으로 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_bind2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="binder1st"></a> binder1st (STL/CLR)

단일 인수 함수를 설명 하는 템플릿 클래스는 호출 된 경우 첫 번째 인수로 저장된 및 제공 된 두 번째 인수를 사용 하 여 호출 하는 저장된 두 인수 함수를 반환 합니다. 사용 하 여 해당 저장된 함수를 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Fun>
    ref class binder1st
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        second_argument_type, result_type>
        delegate_type;

    binder1st(Fun% functor, first_argument_type left);
    binder1st(binder1st<Arg>% right);

    result_type operator()(second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Fun*<br/>
형식 저장된 함수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|
|stored_function_type|함수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|binder1st|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|operator delegate_type^()|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수인 및 첫 번째 인수를 저장 하는 단일 인수 함수를 설명 합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 되도록 저장된 첫 번째 인수 및 제공 된 두 번째 인수를 사용 하 여 저장된 함수를 호출 하는 결과 반환 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_binder1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="binder2nd"></a> binder2nd (STL/CLR)

단일 인수 함수를 설명 하는 템플릿 클래스는 호출 된 경우 제공 된 첫 번째 인수 및 해당 저장 된 두 번째 인수를 사용 하 여 호출 하는 저장된 두 인수 함수를 반환 합니다. 사용 하 여 해당 저장된 함수를 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Fun>
    ref class binder2nd
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        first_argument_type, result_type>
        delegate_type;

    binder2nd(Fun% functor, second_argument_type left);
    binder2nd(binder2nd<Arg>% right);

    result_type operator()(first_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Fun*<br/>
형식 저장된 함수입니다.

## <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|
|stored_function_type|함수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|binder2nd|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|operator delegate_type^()|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수인 및 두 번째 인수를 저장 하는 단일 인수 함수를 설명 합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 되도록 제공 된 첫 번째 인수 및 저장 된 두 번째 인수를 사용 하 여 저장된 함수를 호출 하는 결과 반환 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_binder2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="divides"></a> divides (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 된 경우 두 번째 피연산자로 나눈 첫 번째 인수를 반환 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class divides
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    divides();
    divides(divides<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수 및 반환 값입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|divides|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|operator delegate_type^()|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 두 번째 피연산자로 나눈 첫 번째 인수를 개체 함수로 호출 되 면 반환 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_divides.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::divides<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 3
```

## <a name="equal_to"></a> equal_to (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 하는 첫 번째 인수가 두 번째 경우에 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    equal_to();
    equal_to(equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|equal_to|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|operator delegate_type^()|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 첫 번째 인수가 두 번째 경우.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="greater"></a> 큰 (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 하는 첫 번째 인수는 두 번째 보다 큰 경우에 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class greater
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater();
    greater(greater<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|greater|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 하는 경우 첫 번째 인수가 두 번째 보다 큽니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_greater.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
1 0
```

## <a name="greater_equal"></a> greater_equal (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 합니다만 첫 번째 인수가 두 번째 보다 크거나 같은 경우 인지 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class greater_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater_equal();
    greater_equal(greater_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|greater_equal|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 첫 번째 인수가 두 번째 보다 크거나 같은 경우 인지 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_greater_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="less"></a> less (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 하는 첫 번째 인수는 작은 경우에 두 번째 인스턴스보다 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class less
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less();
    less(less<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|less|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 하는 경우 첫 번째 인수는 작은 두 번째 인스턴스보다 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_less.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="less_equal"></a> less_equal (STL/CLR)

템플릿 클래스를 설명 하는 함수인은 호출 되 면 true를 반환 합니다만 첫 번째 인수가 두 번째 보다 작거나 같은 경우입니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class less_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less_equal();
    less_equal(less_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|less_equal|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 하는 경우 첫 번째 인수가 두 번째 보다 작거나 같은 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_less_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
0 1
```

## <a name="logical_and"></a> logical_and (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 첫 번째 인수와 두 번째 테스트는 모두 true 하는 경우에 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class logical_and
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_and();
    logical_and(logical_and<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|logical_and|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 첫 번째 인수와 두 번째 테스트는 모두 true입니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_logical_and.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 1 0" and " 1 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_and<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
3 0
1 0
```

## <a name="logical_not"></a> logical_not (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 하거나 경우에 해당 인수를 false로 테스트 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class logical_not
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    logical_not();
    logical_not(logical_not<Arg> %right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|argument_type|형식 함수 인수입니다.|
|delegate_type|제네릭 대리자의 형식입니다.|
|result_type|함수 결과의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|logical_not|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 단일 인수 함수를 설명 합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 해당 인수를 false로 테스트 하는 경우.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_logical_not.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::logical_not<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
0 1
```

## <a name="logical_or"></a> logical_or (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 true 첫 번째 인수 또는으로 두 번째 테스트 하는 경우에 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class logical_or
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_or();
    logical_or(logical_or<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|logical_or|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 첫 번째 인수 또는으로 두 번째 테스트 true입니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_logical_or.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(0);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 2 0" and " 0 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_or<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
0 0
1 0
```

## <a name="minus"></a> minus (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 된 경우 첫 번째 인수가 두 번째 뺀 값을 반환 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class minus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    minus();
    minus(minus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수 및 반환 값입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|minus|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 첫 번째 인수가 두 번째 빼기를 개체 함수로 호출 되 면 반환 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_minus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::minus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 2
```

## <a name="modulus"></a> modulus (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 된 경우 두 번째 모듈로 첫 번째 인수를 반환 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class modulus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    modulus();
    modulus(modulus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수 및 반환 값입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|나머지|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 첫 번째 인수가 두 번째 모듈로 개체 함수로 호출 되 면를 반환 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_modulus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(2);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 2" and " 3 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::modulus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 2
3 1
1 0
```

## <a name="multiplies"></a> multiplies (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 된 경우 첫 번째 인수가 두 번째 시간을 반환 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class multiplies
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    multiplies();
    multiplies(multiplies<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수 및 반환 값입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|multiplies|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 첫 번째 인수가 두 번째 시간 개체 함수로 호출 되 면를 반환 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_multiplies.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::multiplies<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
8 3
```

## <a name="negate"></a> negate (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 된 경우 부정 해당 인수를 반환 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class negate
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    negate();
    negate(negate<Arg>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|argument_type|형식 함수 인수입니다.|
|delegate_type|제네릭 대리자의 형식입니다.|
|result_type|함수 결과의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|negate|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 단일 인수 함수를 설명 합니다. 멤버 연산자 정의 `operator()` 부정 인수로 반환 개체를 함수로 호출 될 때에 있도록 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(-3);
    Myvector c3(2, 0);

// display initial contents " 4 -3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::negate<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 -3
-4 3
```

## <a name="not_equal_to"></a> not_equal_to (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환 하는 첫 번째 인수가 두 번째 경우에 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class not_equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    not_equal_to();
    not_equal_to(not_equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|not_equal_to|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 되 면 있도록만 true를 반환 하는 경우 첫 번째 인수가 두 번째 아닙니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_not_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="not1"></a> not1 (STL/CLR)

생성 된 `unary_negate` 있는 함수에 대 한 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Fun>
    unary_negate<Fun> not1(Fun% functor);
```

#### <a name="template-parameters"></a>템플릿 매개 변수

*Fun*<br/>
함수의 형식입니다.

#### <a name="function-parameters"></a>함수 매개 변수

*functor*<br/>
래핑할 함수입니다.

### <a name="remarks"></a>설명

템플릿 함수 [unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)`<Fun>(functor)`합니다. 해당 논리 NOT을 제공 하는 함수에서 단일 인수 함수를 래핑하는 편리한 방법으로 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_not1.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```

## <a name="not2"></a> not2 (STL/CLR)

생성 된 `binary_negate` 있는 함수에 대 한 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Fun>
    binary_negate<Fun> not2(Fun% functor);
```

#### <a name="template-parameters"></a>템플릿 매개 변수

*Fun*<br/>
함수의 형식입니다.

#### <a name="function-parameters"></a>함수 매개 변수

*functor*<br/>
래핑할 함수입니다.

### <a name="remarks"></a>설명

템플릿 함수 [binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)`<Fun>(functor)`합니다. 해당 논리 NOT을 제공 하는 함수에 인수가 두 개인 함수를 래핑하는 편리한 방법으로 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_not2.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="plus"></a> plus (STL/CLR)

함수를 설명 하는 템플릿 클래스는 호출 된 경우 첫 번째 인수 및 두 번째 반환 합니다. 사용 하 여 해당 인수 형식 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Arg>
    ref class plus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    plus();
    plus(plus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
형식 인수 및 반환 값입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|delegate_type|제네릭 대리자의 형식입니다.|
|first_argument_type|첫 번째 함수 인수의 형식입니다.|
|result_type|함수 결과의 형식입니다.|
|second_argument_type|두 번째 함수 인수의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|plus|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 두 인수 함수를 설명합니다. 멤버 연산자 정의 `operator()` 첫 번째 인수 및 두 번째 반환 개체를 함수로 호출 될 때에 있도록 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_plus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::plus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
6 4
```

## <a name="unary_delegate"></a> unary_delegate (STL/CLR)

Genereic 클래스는 단일 인수 대리자를 설명합니다. 사용 하 여 해당 인수 및 반환 형식 기준으로 대리자를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
generic<typename Arg,
    typename Result>
    delegate Result unary_delegate(Arg);
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
인수 형식입니다.

*결과*<br/>
반환 형식입니다.

### <a name="remarks"></a>설명

Genereic 대리자는 단일 인수 함수를 설명합니다.

note:

`unary_delegare<int, int> Fun1;`

`unary_delegare<int, int> Fun2;`

형식을 `Fun1` 고 `Fun2` 은 동의어 이며에 대 한 동안:

`delegate int Fun1(int);`

`delegate int Fun2(int);`

동일한 형식 하지 않습니다.

### <a name="example"></a>예제

```cpp
// cliext_unary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

int hash_val(wchar_t val)
    {
    return ((val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate<wchar_t, int> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 5
hash(L'b') = 22
```

## <a name="unary_delegate_noreturn"></a> unary_delegate_noreturn (STL/CLR)

Genereic 클래스를 반환 하는 단일 인수 대리자 설명 **void**합니다. 사용 하 여 해당 인수 형식 측면에서 대리자를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
generic<typename Arg>
    delegate void unary_delegate_noreturn(Arg);
```

#### <a name="parameters"></a>매개 변수

*Arg*<br/>
인수 형식입니다.

### <a name="remarks"></a>설명

Genereic 대리자에 반환 하는 단일 인수 함수에 설명 **void**합니다.

note:

`unary_delegare_noreturn<int> Fun1;`

`unary_delegare_noreturn<int> Fun2;`

형식을 `Fun1` 고 `Fun2` 은 동의어 이며에 대 한 동안:

`delegate void Fun1(int);`

`delegate void Fun2(int);`

동일한 형식 하지 않습니다.

### <a name="example"></a>예제

```cpp
// cliext_unary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void hash_val(wchar_t val)
    {
    System::Console::WriteLine("hash({0}) = {1}",
       val, (val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    myhash(L'a');
    myhash(L'b');
    return (0);
    }
```

```Output
hash(a) = 5
hash(b) = 22
```

## <a name="unary_negate"></a> unary_negate (STL/CLR)

템플릿 클래스를 설명 하는 함수인은 호출 된 경우 반환 논리적 해당 저장 된 단일 인수 함수는 아닙니다. 사용 하 여 해당 저장된 함수를 기준으로 함수 개체를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Fun>
    ref class unary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::argument_type argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    unary_negate(Fun% functor);
    unary_negate(unary_negate<Fun>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>매개 변수

*Fun*<br/>
형식 저장된 함수입니다.

### <a name="member-functions"></a>멤버 함수

|형식 정의|설명|
|---------------------|-----------------|
|argument_type|형식 함수 인수입니다.|
|delegate_type|제네릭 대리자의 형식입니다.|
|result_type|함수 결과의 형식입니다.|

|멤버|설명|
|------------|-----------------|
|unary_negate|함수를 생성합니다.|

|연산자|설명|
|--------------|-----------------|
|operator()|원하는 함수를 계산합니다.|
|delegate_type^|대리자에 함수를 캐스팅합니다.|

### <a name="remarks"></a>설명

템플릿 클래스는 다른 단일 인수 함수를 저장 하는 단일 인수 함수를 설명 합니다. 멤버 연산자 정의 `operator()` 논리적 반환 개체 함수로 호출 되 면 있도록의 저장 된 함수 인수를 사용 하 여 호출 합니다.

함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.

### <a name="example"></a>예제

```cpp
// cliext_unary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```