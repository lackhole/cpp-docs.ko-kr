---
title: 할당
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
ms.openlocfilehash: 1e6d715011cfaab7e250e23a9a31bb3f0c83f36a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184341"
---
# <a name="assignment"></a>할당

대입 연산자 (**=**)는 엄밀 하, 이항 연산자입니다. 할당 연산자의 선언은 다음을 제외하고 다른 모든 이항 연산자와 동일합니다.

- 비정적 멤버 함수여야 합니다. 아니오 **연산자 =** 비멤버 함수로 선언할 수 있습니다.
- 파생 클래스가 상속하지 않습니다.
- 기본값 **연산자 =** 존재 하지 않는 경우 클래스 형식에 대 한 컴파일러에서 함수를 생성할 수 있습니다.

다음 예제에서는 할당 연산자를 선언하는 방법을 보여 줍니다.

```cpp
class Point
{
public:
    int _x, _y;

    // Right side of copy assignment is the argument.
    Point& operator=(const Point&);
};

// Define copy assignment operator.
Point& Point::operator=(const Point& otherPoint)
{
    _x = otherPoint._x;
    _y = otherPoint._y;

    // Assignment operator returns left side of assignment.
    return *this;
}

int main()
{
    Point pt1, pt2;
    pt1 = pt2;
}
```

제공 된 인수 식의 오른쪽에 있는 경우 연산자는 개체를 반환하여 할당 연산자의 동작을 보존하고, 할당 연산자는 할당이 완료된 후 왼쪽의 값을 반환합니다. 이렇게 하면 같은 할당의 연결.

```cpp
pt1 = pt2 = pt3;
```

복사 할당 연산자 복사 생성자와 혼동 해서는 안 됩니다. 후자에서 호출 되는 새 개체를 생성 하는 동안 기존:

```cpp
// Copy constructor is called--not overloaded copy assignment operator!
Point pt3 = pt1;

// The previous initialization is similar to the following:
Point pt4(pt1); // Copy constructor call.
```

> [!NOTE]
> 따라야 하는 것이 좋습니다 합니다 [3의 규칙](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) 클래스 복사 할당 연산자를 정의 하는 복사 생성자를 명시적으로 정의 해야 소멸자와으로, C + + 11부터 이동 생성자 및 이동 할당 연산자입니다.

## <a name="see-also"></a>참고자료

- [연산자 오버로드](../cpp/operator-overloading.md)
- [복사 생성자 및 복사 할당 연산자(C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)