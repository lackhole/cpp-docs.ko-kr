---
title: bad_cast 예외
ms.date: 11/04/2016
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: b40f64671e7c259b7dc04b31a11d20d0fc76c5c4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68242390"
---
# <a name="badcast-exception"></a>bad_cast 예외

**bad_cast** 예외는 참조 형식에 대한 실패한 캐스팅 결과로 **dynamic_cast** 연산자가 throw합니다.

## <a name="syntax"></a>구문

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>설명

**bad_cast**의 인터페이스는 다음과 같습니다.

```cpp
class bad_cast : public exception
```

다음 코드에는 **bad_cast** 예외를 throw하는 실패한 **dynamic_cast**의 예제가 포함되어 있습니다.

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo.h>
#include <iostream>

class Shape {
public:
   virtual void virtualfunc() const {}
};

class Circle: public Shape {
public:
   virtual void virtualfunc() const {}
};

using namespace std;
int main() {
   Shape shape_instance;
   Shape& ref_shape = shape_instance;
   try {
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);
   }
   catch (bad_cast b) {
      cout << "Caught: " << b.what();
   }
}
```

캐스팅될 개체(모양)가 지정된 캐스트 형식(원)에서 파생되지 않으므로 예외가 throw됩니다. 예외를 방지하려면 `main`에 다음과 같은 선언을 추가합니다.

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

그리고 나서 다음과 같이 **try** 블록의 캐스트 감각을 반전시킵니다.

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[bad_cast](#bad_cast)|`bad_cast` 형식의 개체에 대한 생성자입니다.|

### <a name="functions"></a>함수

|기능|Description|
|-|-|
|[what](#what)|TBD|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator=](#op_eq)|하나를 할당 하는 대입 연산자 `bad_cast` 다른 개체입니다.|

## <a name="bad_cast"></a> bad_cast

`bad_cast` 형식의 개체에 대한 생성자입니다.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a> 연산자 =

하나를 할당 하는 대입 연산자 `bad_cast` 다른 개체입니다.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a> 새로운

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>참고자료

[dynamic_cast 연산자](../cpp/dynamic-cast-operator.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[C++ 예외 처리](../cpp/cpp-exception-handling.md)