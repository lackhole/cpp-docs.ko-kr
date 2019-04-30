---
title: override 지정자
ms.date: 11/04/2016
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
ms.openlocfilehash: 71505f8b9b4dc2800e80a78a64f0ca6984af1349
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345864"
---
# <a name="override-specifier"></a>override 지정자

**override** 키워드를 사용하여 기본 클래스에서 가상 함수를 재정의하는 멤버 함수를 지정할 수 있습니다.

## <a name="syntax"></a>구문

```
function-declaration override;
```

## <a name="remarks"></a>설명

**override**는 상황에 따라 달라지며 멤버 함수 선언 뒤에 사용할 경우에만 특별한 의미가 있으며 그렇지 않으면 예약된 키워드가 아닙니다.

## <a name="example"></a>예제

**override**를 사용하여 코드에서 부주의한 상속 동작이 생기지 않도록 합니다. 다음 예제에서는 **override**를 사용하지 않아 의도하지 않은 파생 클래스의 멤버 함수 동작이 발생하는 경우를 보여 줍니다. 컴파일러는 이 코드의 오류를 내보내지 않습니다.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA(); // ok, works as intended

    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not
                          // override BaseClass::funcB() const and it is a new member function

    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different
                                      // parameter type than BaseClass::funcC(int), so
                                      // DerivedClass::funcC(double) is a new member function
};
```

**override**를 사용하면 컴파일러가 자동으로 새 멤버 함수를 만드는 대신 오류를 생성합니다.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA() override; // ok

    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not
                                   // override BaseClass::funcB() const

    virtual void funcC( double = 0.0 ) override; // compiler error:
                                                 // DerivedClass::funcC(double) does not
                                                 // override BaseClass::funcC(int)

    void funcD() override; // compiler error: DerivedClass::funcD() does not
                           // override the non-virtual BaseClass::funcD()
};
```

함수를 재정의할 수 없으며 클래스를 상속할 수 없도록 지정하려면 [final](../cpp/final-specifier.md) 키워드를 사용하세요.

## <a name="see-also"></a>참고 항목

[final 지정자](../cpp/final-specifier.md)<br/>
[키워드(C++)](../cpp/keywords-cpp.md)