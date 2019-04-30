---
title: 템플릿 (C++)
ms.date: 11/04/2016
f1_keywords:
- template_cpp
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
ms.openlocfilehash: f1532b5aa4ea712feab08b49b7c035187ca0d042
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330494"
---
# <a name="templates-c"></a>템플릿 (C++)

템플릿은 C++의 제네릭 프로그래밍에 대한 기준입니다. 강력한 언어와 C++는 특정 형식 선언 프로그래머가 명시적으로 또는 컴파일러에 의해 추론된 모든 변수가 필요합니다. 그러나 많은 데이터 구조 및 알고리즘 확인에서 작동하는 유형과 관계없이 동일합니다. 이러한 작업 형식 함수나 클래스의 작업을 정의하고 사용자가 어떤 구체적인 지정을 할 수 있는 템플릿을 사용하면 작동해야 합니다.

## <a name="defining-and-using-templates"></a>정의 및 템플릿 사용

템플릿은은 템플릿 매개 변수는 사용자가 제공 하는 인수를 기준으로 하는 컴파일 시간에는 일반 형식 또는 함수를 생성 하는 구문입니다. 예를 들어, 다음과 같은 함수 템플릿을 정의할 수 있습니다.

```cpp
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

위의 코드는 단일 형식 매개 변수를 사용 하 여 일반 함수에 대 한 템플릿을 설명 *T*, 해당 값을 반환 하 고 호출 (lhs 및 rhs) 매개 변수는이 형식의 모든 합니다. 이름은 형식 매개 변수 규칙 단일 대문자나 소문자 문자로 아니라 등 가장 흔히 사용 됩니다. *T* 는 템플릿 매개 변수를 **typename** 키워드 64f6eb0d이 매개 변수 형식에 대 한 자리 표시자입니다. 컴파일러의 모든 인스턴스를 대체할 함수를 호출 하면 `T` 사용자가 지정 되었거나 컴파일러에 의해 추론 된 하는 구체적인 형식 인수를 사용 하 여 합니다. 컴파일러는 클래스를 생성 하거나 템플릿에서 함수 라고 하는 프로세스 *템플릿 인스턴스화*; `minimum<int>` 은 템플릿 인스턴스화 `minimum<T>`합니다.

다른 곳에서 사용자는 int 특수화 된 템플릿의 인스턴스를 선언할 수 있습니다. Get_a()와 get_b() int를 반환 하는 함수는 가정 합니다.

```cpp
int a = get_a();
int b = get_b();
int i = minimum<int>(a, b);
```

그러나 이기 때문에 함수 템플릿과 컴파일러 수의 형식을 추론할 `T` 인수에서 *를* 하 고 *b*는 일반 함수 처럼 호출할 수 있습니다.

```cpp
int i = minimum(a, b);
```

컴파일러는 마지막 문이 발견의 모든 항목에 새 함수 생성 *T* 템플릿에서 바뀝니다 **int**:

```cpp
int minimum(const int& lhs, const int& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

컴파일러가 함수 템플릿의 형식 추론을 수행 하는 방법에 대 한 규칙은 일반 함수에 대 한 규칙을 기반으로 합니다. 자세한 내용은 [오버 로드 확인 함수 템플릿 호출](../cpp/overload-resolution-of-function-template-calls.md)합니다.

## <a id="type_parameters"></a> 형식 매개 변수

에 `minimum` 유의 위의 템플릿 형식 매개 변수 *T* const 및 참조 한정자가 추가 된 함수 호출 매개 변수에서 사용 될 때까지 어떤 방식으로 한정 되지 않습니다.

형식 매개 변수 수에 제한이 있습니다. 여러 매개 변수를 쉼표로 구분 합니다.

```cpp
template <typename T, typename U, typename V> class Foo{};
```

키워드 **클래스** 같습니다 **typename** 이 컨텍스트에서 합니다. 이전 예제를 표현할 수 있습니다.

```cpp
template <class T, class U, class V> class Foo{};
```

임의 개수의 0 개 이상의 형식 매개 변수를 사용 하는 템플릿을 정의 하는 줄임표 연산자 (...)를 사용할 수 있습니다.

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

모든 기본 제공 또는 사용자 정의 형식은 형식 인수로 사용할 수 있습니다. 정수, double, 문자열을 저장 하려면 표준 라이브러리에서 std:: vector를 사용할 수는 예를 들어 MyClass, const MyClass *, MyClass & 합니다. 기본 제한 때 템플릿을 사용 하 여 형식 인수에서 형식 매개 변수에 적용 되는 모든 작업을 지원 해야 한다는입니다. 예를 들어, 최소 호출 하는 경우이 예제와 같이 MyClass를 사용 하 여:

```cpp
class MyClass
{
public:
    int num;
    std::wstring description;
};

int main()
{
    MyClass mc1 {1, L"hello"};
    MyClass mc2 {2, L"goodbye"};
    auto result = minimum(mc1, mc2); // Error! C2678
}
```

MyClass에 대 한 오버 로드를 제공 하지 않기 때문에 컴파일러 오류가 발생 합니다 < 연산자입니다.

요구 사항은 없습니다 내재 된 모든 특정 템플릿에 대 한 형식 인수를 동일한 개체 계층 구조에 속해 있는지는 이러한 제한 사항을 적용 하는 템플릿을 정의할 수 있지만. 개체 지향 기술을 템플릿으로; 결합할 수 있습니다. 예를 들어, 저장할 수 있습니다 파생 * 벡터에 있는\<자료\*>.    인수 포인터 해야

```cpp
vector<MyClass*> vec;
   MyDerived d(3, L"back again", time(0));
   vec.push_back(&d);

   // or more realistically:
   vector<shared_ptr<MyClass>> vec2;
   vec2.push_back(make_shared<MyDerived>());
```

벡터 및 기타 표준 라이브러리 컨테이너의 요소에 적용 하는 기본 요구 사항을 `T` 는 `T` 복사 할당 가능 하 고 복사 생성 가능 합니다.

## <a name="non-type-parameters"></a>비형식 매개 변수

C# 및 Java와 같은 다른 언어로 제네릭 형식과 달리 C++ 템플릿은 값 매개변수라고도 하는 비형식 매개변수를 지원합니다. 예를 들어, std:: array 클래스는 표준 라이브러리에 이 예제에서와 마찬가지로 배열의 길이를 지정하는 상수 정수 값을 제공할 수 있습니다.

```cpp
template<typename T, size_t L>
class MyArray
{
    T arr[L];
public:
    MyArray() { ... }
};
```

템플릿 선언의 구문을 note 합니다. Size_t 값에서 컴파일 타임에 템플릿 인수로 전달 되 고 상수 또는 constexpr 식 이어야 합니다. 다음과 같이 사용합니다.

```cpp
MyArray<MyClass*, 10> arr;
```

다른 종류의 포인터 및 참조를 포함 하 여 값 형식이 아닌 매개 변수로 전달할 수 있습니다. 예를 들어, 함수 또는 함수 템플릿 코드 내에서 일부 작업을 사용자 지정 하는 개체에 대 한 포인터에 전달할 수 있습니다.

## <a id="template_parameters"></a> 템플릿 매개 변수로 템플릿

템플릿에 템플릿 매개 변수를 수 있습니다. 이 예제에서는 MyClass2에 두 개의 템플릿 매개 변수: typename 매개 변수 *T* 템플릿 매개 변수 *Arr*:

```cpp
template<typename T, template<typename U, int I> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
    U u; //Error. U not in scope
};
```

때문에 합니다 *Arr* 매개 변수 자체에 본문이 없습니다, 해당 매개 변수 이름이 필요 하지 않습니다. 오류가 참조 하는 것이 사실 *Arr*의 본문 내에서 있는 typename 또는 클래스 매개 변수 이름은 `MyClass2`합니다. 이러한 이유로 *Arr*의이 예제와 같이 형식 매개 변수 이름을 생략할 수 있습니다.

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## <a name="default-template-arguments"></a>기본 템플릿 인수

클래스 및 함수 템플릿을 기본 인수를 가질 수 있습니다. 템플릿을 그대로 두면 기본 인수에 사용할 경우를 지정 합니다. 예를 들어, std:: vector 템플릿 인수가 기본 할당자에 대해:

```cpp
template <class T, class Allocator = allocator<T>> class vector;
```

대부분의 경우 기본 std:: allocator 클래스는 다음과 같은 벡터를 사용 하도록 허용:

```cpp
vector<int> myInts;
```

하지만 경우 필요한 지정할 수 있습니다 사용자 지정 할당자를 같습니다.

```cpp
vector<int, MyAllocator> ints;
```

템플릿 인수가 여러 개인 경우 첫 번째 기본 인수 다음의 모든 인수에는 기본 인수가 있어야 합니다.

매개 변수를 가진 모든 기본값으로 템플릿을 사용 하는 경우 빈 꺾쇠 괄호를 사용 합니다.

```cpp
template<typename A = int, typename B = double>
class Bar
{
    //...
};
...
int main()
{
    Bar<> bar; // use all default type arguments
}
```

## <a name="template-specialization"></a>템플릿 특수화

경우에 따라 불가능 하거나 바람직하지 않은 모든 형식에 대 한 동일한 코드를 정의 하는 템플릿은 없습니다. 예를 들어, 특정 기본 클래스에서 파생 된 형식 또는 형식 인수는 포인터 또는 std:: wstring을 하는 경우에 실행할 코드 경로 정의 하고자 할 수 있습니다.  이러한 경우 정의할 수 있습니다는 *특수화* 해당 특정 형식에 대 한 템플릿. 사용자는 해당 형식을 사용 하 여 템플릿을 인스턴스화하고, 컴파일러는 클래스를 생성 하는 특수화를 사용 하 고 다른 모든 형식의 경우 컴파일러는 일반 템플릿 선택 합니다. 모든 매개 변수는 특수화 된 특수화 된 *특수화 완료*합니다. 일부 매개 변수는 특수화 된 경우 호출 되는 *부분 특수화*합니다.

```cpp
template <typename K, typename V>
class MyMap{/*...*/};

// partial specialization for string keys
template<typename V>
class MyMap<string, V> {/*...*/};
...
MyMap<int, MyClass> classes; // uses original template
MyMap<string, MyClass> classes2; // uses the partial specialization
```

서식으로 각 특수화 된 형식 매개 변수는 고유 개수에 관계 없이 특수화 있을 수 있습니다. 클래스 템플릿 부분적으로 특수화 될 수 있습니다. 템플릿의 모든 전체 및 부분 특수화는 원본 템플릿과 동일한 네임 스페이스에서 선언 되어야 합니다.

자세한 내용은 [템플릿 특수화](../cpp/template-specialization-cpp.md)합니다.
