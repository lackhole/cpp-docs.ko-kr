---
title: this 포인터
ms.date: 11/04/2016
f1_keywords:
- this_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
ms.openlocfilehash: c90a843ba978a98c1c61d9e096d62b85256ab0c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330481"
---
# <a name="this-pointer"></a>this 포인터

**이** 포인터가 대 한 포인터의 비정적 멤버 함수 내 에서만 액세스할 수는 **클래스**, **구조체**, 또는 **union** 형식입니다. 멤버 함수가 호출되는 개체를 가리킵니다. 없는 정적 멤버 함수는 **이** 포인터입니다.

## <a name="syntax"></a>구문

```cpp
this
this->member-identifier
```

## <a name="remarks"></a>설명

개체의 **이** 포인터 개체 자체의 일부가 아닙니다. 결과에 반영 되지 않습니다는 **sizeof** 개체의 문입니다. 대신 비정적 멤버 함수가 개체에 대해 호출되는 경우 컴파일러가 개체의 주소를 숨겨진 인수로 함수에 전달합니다. 예를 들어, 다음 함수 호출은

```cpp
myDate.setMonth( 3 );
```

이렇게 해석할 수 있습니다.

```cpp
setMonth( &myDate, 3 );
```

개체의 주소는 멤버 함수 내에서 사용할 수는 **이** 포인터입니다. 대부분의 용도 **이** 암시 합니다. 하지만 명시적으로 사용 하 여 불필요 한 것이 유효 **이** 클래스의 멤버를 참조할 때. 예를 들어:

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   this->month = mn;      // are equivalent
   (*this).month = mn;
}
```

멤버 함수에서 현재 개체를 반환하기 위해 `*this` 식이 주로 사용됩니다.

```cpp
return *this;
```

합니다 **이** 포인터는 또한 자체 참조에 대 한 보호 하는 데 사용 됩니다.

```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

> [!NOTE]
>  때문에 **이** 포인터는 수정할 수 없는, 할당할 **이** 허용 되지 않습니다. 이전 구현에서는 C++ 에 할당할 수 있었습니다 **이렇게**합니다.

경우에 따라 합니다 **이** 포인터를 직접 사용-예를 들어, 자기 참조 데이터를 조작 하 구조를 현재 개체의 주소가 필요 합니다.

## <a name="example"></a>예제

```cpp
// this_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

class Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( const Buf & );
    void Display() { cout << buffer << endl; }

private:
    char*   buffer;
    size_t  sizeOfBuffer;
};

Buf::Buf( char* szBuffer, size_t sizeOfBuffer )
{
    sizeOfBuffer++; // account for a NULL terminator

    buffer = new char[ sizeOfBuffer ];
    if (buffer)
    {
        strcpy_s( buffer, sizeOfBuffer, szBuffer );
        sizeOfBuffer = sizeOfBuffer;
    }
}

Buf& Buf::operator=( const Buf &otherbuf )
{
    if( &otherbuf != this )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *this;
}

int main()
{
    Buf myBuf( "my buffer", 10 );
    Buf yourBuf( "your buffer", 12 );

    // Display 'my buffer'
    myBuf.Display();

    // assignment operator
    myBuf = yourBuf;

    // Display 'your buffer'
    myBuf.Display();
}
```

```Output
my buffer
your buffer
```

## <a name="type-of-the-this-pointer"></a>this 포인터 형식

**이** 포인터의 형식에서 함수 선언을 수정할 수 있습니다 합니다 **const** 하 고 **volatile** 키워드. 이러한 키워드 하나 이상의 특성을 포함하도록 함수를 선언하려면 함수 인수 목록 뒤에 키워드를 추가합니다.

다음 예제를 고려해 보세요.

```cpp
// type_of_this_pointer1.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

앞의 코드는 멤버 함수를 선언 `X`는 합니다 **이** 포인터로 처리 됩니다는 **const** 에 대 한 포인터를 **const** 개체입니다. 조합을 *cv mod 목록* 옵션을 사용할 수 있지만 항상 가리키는 개체를 수정할 **이**아니라는 **이** 포인터 자체입니다. 따라서 다음 선언은 함수를 선언 `X`; **이** 포인터가 **const** 에 대 한 포인터를 **const** 개체:

```cpp
// type_of_this_pointer2.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

유형의 **이** 멤버 함수는 다음 구문으로 설명 위치 *cv 한정자 목록* 멤버 함수 선언 자에서 결정 되 고 수 **const**또는 **volatile** (또는 둘 다) 및 *클래스 형식* 클래스의 이름입니다.

*[cv 한정자 목록] 클래스 형식* **&#42; const이**

다시 말해 **이** 는 항상 const 포인터 이며 다시 할당할 수 없습니다.  **상수** 또는 **volatile** 멤버 함수 선언에 사용 되는 한정자가 가리키는 클래스 인스턴스에 적용 **이** 해당 함수 범위의 합니다.

다음 표에서 이러한 한정자의 작동 방식에 대해 자세히 설명합니다.

### <a name="semantics-of-this-modifiers"></a>한정자의 의미

|한정자|의미|
|--------------|-------------|
|**const**|멤버 데이터를 변경할 수 없습니다. 되지 않는 멤버 함수를 호출할 수 없습니다 **const**합니다.|
|**volatile**|액세스할 때마다 메모리에서 멤버 데이터를 로드하고 특정 최적화를 비활성화합니다.|

전달 하면 오류가 발생 한 **const** 하지 않은 멤버 함수에 개체 **const**. 마찬가지로 것은 오류를 전달 하는 **volatile** 하지 않은 멤버 함수에 개체 **volatile**.

로 선언 된 멤버 함수 **const** 멤버 데이터를 변경할 수 없습니다-이러한 함수는 **이** 포인터가에 대 한 포인터를 **const** 개체입니다.

> [!NOTE]
>  생성자 및 소멸자로 선언할 수 없습니다 **상수** 하거나 **volatile**합니다. 그러나 될 수 있습니다 호출 **상수** 또는 **volatile** 개체입니다.

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)