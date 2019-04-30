---
title: Trivial, 표준 레이아웃, POD를 및 리터럴 형식
ms.date: 04/05/2018
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: c742f4c84a1b2ba558b790d7eea7760902da7818
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266766"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>Trivial, 표준 레이아웃, POD를 및 리터럴 형식

용어 *레이아웃* 클래스, 구조체 또는 공용 구조체 형식 개체의 멤버를 메모리에 정렬 되는 방식을 가리킵니다. 경우에 따라 레이아웃 언어 사양에 잘 정의 된 경우 클래스 또는 구조체에 있는 경우 특정 하지만 C++ 가상 기본 클래스, 가상 함수, 다른 액세스 제어를 사용 하 여 멤버와 같은 언어 기능을 컴파일러는 레이아웃을 선택 합니다. 해당 레이아웃 수행 되는 최적화에 따라 달라질 수 있습니다 및 대부분의 개체 수도 차지 하지는 인접 한 메모리 영역입니다. 예를 들어, 클래스에 가상 함수가 있으면 해당 클래스의 모든 인스턴스를 단일 가상 함수 테이블을 공유할 수 있습니다. 이러한 형식은 물론 매우 유용 하지만 수도 제한 사항을 갖습니다. 레이아웃 정의 되지 않으므로 C와 같은 다른 언어로 작성 된 프로그램에 전달할 수 없습니다 및 불연속 있을 수 있으므로 복사할 수는 없습니다 안정적으로 빠르게 하위 수준 함수를 사용 하 여 같은 `memcopy` 되거나 네트워크를 통해 serialize 합니다.

컴파일러를 사용 하도록 설정 하려면 뿐만 C++ 프로그램 및 C + + 14 도입 간단한 클래스 및 구조체의 세 가지 범주는 특정 메모리 레이아웃에 종속 된 작업에 대 한 지정 된 형식의 적합성에 대 한 이유를 metaprograms: *trivial* 하십시오 *표준 레이아웃*, 및 *POD* 또는 Plain Old Data. 표준 라이브러리에 함수 템플릿이 `is_trivial<T>`하십시오 `is_standard_layout<T>` 및 `is_pod<T>` 지정된 된 형식 지정된 된 범주에 속하는지 여부를 결정 하는 합니다.

## <a name="trivial-types"></a>Trivial 형식

클래스 또는 구조체의 경우 C++ 컴파일러에서 제공 하거나 명시적으로 기본값으로 설정 된 특수 멤버 함수에 다음 형식이 trivial 형식인 합니다. 인접 한 메모리 영역을 차지 합니다. 이 서로 다른 액세스 지정자를 사용 하 여 멤버를 가질 수 있습니다. C++, 컴파일러는이 상황에서 멤버를 정렬 하는 방법을 선택할 수 있습니다. 따라서 이러한 개체 memcopy 수는 있지만 C 프로그램에서 안정적으로 사용할 수 없습니다. Trivial 형식 T char 또는 부호 없는 문자 배열에 복사 하 고 안전 하 게 T 변수로 다시 복사 될 수 있습니다. 맞춤 요구 사항으로 인해, 형식 멤버 간에 패딩 바이트 수 있습니다.

Trivial 형식은 trivial 기본 생성자, trivial 복사 생성자, trivial 복사 할당 연산자 및 trivial 소멸자가 있습니다. 각 예에서 *trivial* 생성자/연산자/소멸자 사용자가 제공한 아니며 있는 클래스에 속하는 의미 합니다.

- 가상 함수나 가상 기본 클래스 없음

- 해당 특수 생성자/연산자/소멸자를 사용 하 여 기본 클래스 없음

- 해당 특수 생성자/연산자/소멸자를 사용 하 여 클래스 형식의 데이터 멤버 없음

다음 예제에서는 trivial 형식 Trivial2의 현재 상태에에서는 `Trivial2(int a, int b)` 생성자는 기본 생성자를 제공 해야 합니다. Trivial로 한 정하는 형식에 대 한 생성자를 명시적으로 기본값으로 해야 있습니다.

```cpp
struct Trivial
{
      int i;
private:
   int j;
   };

struct Trivial2
{
   int i;
   Trivial2(int a, int b) : i(a), j(b) {}
   Trivial2() = default;
   private:
   int j;   // Different access control
};
```

## <a name="standard-layout-types"></a>표준 레이아웃 형식

클래스 또는 구조체에 포함 없을 때 특정 C++ C 언어에서 제공 하지 않는 가상 함수와 같은 언어 기능 및 모든 멤버에 게 동일한 액세스 제어, 표준 레이아웃 형식입니다. Memcopy 수 이며 레이아웃 C 프로그램에서 사용할 수 있는지를 충분히 정의 됩니다. 표준 레이아웃 형식 사용자 정의 특수 멤버 함수를 사용할 수도 있습니다. 또한 표준 레이아웃 형식에 이러한 특성이 있습니다.

- 가상 함수나 가상 기본 클래스 없음

- 동일한 액세스 권한이 모든 비정적 데이터 멤버

- 클래스 형식의 모든 비정적 멤버는 표준 레이아웃

- 모든 기본 클래스는 표준 레이아웃

- 첫 번째 비정적 데이터 멤버와 동일한 형식의 기본 클래스가 없고에 있습니다.

- 이러한 조건 중 하나를 충족합니다.

  - 비정적 데이터 멤버를 사용 하 여 가장 많이 파생 된 클래스 및 둘 이상의 기본 클래스의 비정적 데이터 멤버가 없는 또는

  - 에 비정적 데이터 멤버를 사용 하 여 기본 클래스 없음

다음 코드는 표준 레이아웃 형식의 한 가지 예를 보여줍니다.

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};
```

마지막으로 두 가지 요구 사항이 코드로 더 설명할 아마도 있습니다. 다음 예에서 자료는 표준 레이아웃 `Derived` 아니므로 표준 레이아웃 모두 it (가장 많이 파생 된 클래스) 및 `Base` 비정적 데이터 멤버가 있는 합니다.

```cpp
struct Base
{
   int i;
   int j;
};

// std::is_standard_layout<<Derived> == false!
struct Derived : public Base
{
   int x;
   int y;
};
```

이 예제의 `Derived` 표준 레이아웃 있으므로 `Base` 비정적 데이터 멤버가 없습니다.

```cpp
struct Base
{
   void Foo() {}
};

// std::is_standard_layout<<Derived> == true
struct Derived : public Base
{
   int x;
   int y;
};
```

파생 된 표준 레이아웃도 되는 경우 `Base` 있었습니다 데이터 멤버 및 `Derived` 멤버 함수만 했습니다.

## <a name="pod-types"></a>POD 형식

클래스 또는 구조체에는 간단한 문제가 아니며 표준 레이아웃 되 면에 POD (Plain Old Data) 형식입니다. POD 형식의 메모리 레이아웃은 연속 따라서 및 각 구성원에 게 이러한 형식에서 바이트 복사 되도록 앞에 선언 된 멤버와 이진 I/O를 수행할 수 있습니다 보다 더 높은 주소입니다.  스칼라 예: int 형식은 또한 POD 형식입니다. 클래스는 POD 형식 비정적 데이터 멤버로 POD 유형만 가질 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 trivial, 표준 레이아웃 간의 차이점 및 POD 형식:

```cpp
#include <type_traits>
#include <iostream>

using namespace std;

struct B
{
protected:
   virtual void Foo() {}
};

// Neither trivial nor standard-layout
struct A : B
{
      int a;
   int b;
   void Foo() override {} // Virtual function
};

// Trivial but not standard-layout
struct C
   {
      int a;
private:
   int b;   // Different access control
};

// Standard-layout but not trivial
struct D
{
   int a;
   int b;
   D() {} //User-defined constructor
};

struct POD
{
   int a;
   int b;
};

int main()
{
   cout << boolalpha;
   cout << "A is trivial is " << is_trivial<A>() << endl; // false
   cout << "A is standard-layout is " << is_standard_layout<A>() << endl;  // false

   cout << "C is trivial is " << is_trivial<C>() << endl; // true
   cout << "C is standard-layout is " << is_standard_layout<C>() << endl;  // false

   cout << "D is trivial is " << is_trivial<D>() << endl;  // false
   cout << "D is standard-layout is " << is_standard_layout<D>() << endl; // true

   cout << "POD is trivial is " << is_trivial<POD>() << endl; // true
   cout << "POD is standard-layout is " << is_standard_layout<POD>() << endl; // true

   return 0;
}
```

## <a name="literal_types"></a> 리터럴 형식

리터럴 형식은 컴파일 타임에 해당 레이아웃이 결정될 수 있는 형식입니다. 다음은 리터럴 형식입니다.

- void
- 스칼라 형식
- 참조
- void, 스칼라 형식 또는 참조의 배열
- trivial 소멸자 및 이동 또는 복사 생성자가 아닌 constexpr 생성자를 하나 이상 포함하는 클래스입니다. 또한 해당 비정적 데이터 멤버 및 기본 클래스가 모두 리터럴 형식이고 volatile이 아니어야 합니다.

## <a name="see-also"></a>참고자료

[기본 개념](../cpp/basic-concepts-cpp.md)