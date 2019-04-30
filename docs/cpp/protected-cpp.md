---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 1cbe88a80b83caa78972d1e2799c1e0d87d1cb0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244530"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>구문

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>설명

**보호** 키워드의 클래스 멤버에 대 한 액세스를 지정 합니다 *멤버 목록* 까지 다음 액세스 지정자 (**공용** 또는 **개인**) 또는 클래스 정의의 끝입니다. 로 선언 된 클래스 멤버 **보호** 다음 에서만 사용할 수 있습니다.

- 원래 이 멤버를 선언한 클래스의 멤버 함수

- 원래 이 멤버를 선언한 클래스의 friend

- 원래 이 멤버를 선언한 클래스에서 공용 또는 보호된 액세스로 파생된 클래스

- 보호된 멤버에 대해 전용 액세스 권한이 있으며 전용으로 직접 파생된 클래스

이름 앞에 오는 기본 클래스의 경우는 **보호** 키워드는 기본 클래스의 public 및 protected 멤버는 파생된 클래스의 protected 멤버를 지정 합니다.

보호 된 멤버 만큼 전용 되지 **사설** 선언 된 있지만 만큼 공용도 없는 클래스의 멤버에만 액세스할 수 있는 멤버 **공용** 멤버에 액세스할 수 있는 모든 함수입니다.

보호 된으로 선언 된 멤버 **정적** 모든 파생된 클래스의 friend 나 멤버 함수에 액세스할 수 있습니다. 으로 선언 되지 않은 멤버를 보호 **정적** friend와 멤버 함수 포인터, 참조 또는 파생된 클래스의 개체를 통해서만 파생된 클래스에서 액세스할 수 있습니다.

관련 정보를 참조 하세요 [friend](../cpp/friend-cpp.md), [공용](../cpp/public-cpp.md)를 [개인](../cpp/private-cpp.md), 및 멤버 액세스 테이블 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) .

## <a name="clr-specific"></a>/clr 관련

CLR 형식에는 C++ 액세스 지정자 키워드 (**공용**를 **개인**, 및 **보호**) 형식 및 어셈블리와 관련 된 메서드 표시 여부에 영향을 줄 수 있습니다. 자세한 내용은 [멤버 Access Control](member-access-control-cpp.md)합니다.

> [!NOTE]
>  파일을 컴파일하면 [/LN](../build/reference/ln-create-msil-module.md) 이 동작의 영향을 받지 않습니다. 이 경우 관리되는 클래스(공용 또는 전용)가 모두 표시됩니다.

## <a name="end-clr-specific"></a>END /clr 관련

## <a name="example"></a>예제

```cpp
// keyword_protected.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class X {
public:
   void setProtMemb( int i ) { m_protMemb = i; }
   void Display() { cout << m_protMemb << endl; }
protected:
   int  m_protMemb;
   void Protfunc() { cout << "\nAccess allowed\n"; }
} x;

class Y : public X {
public:
   void useProtfunc() { Protfunc(); }
} y;

int main() {
   // x.m_protMemb;         error, m_protMemb is protected
   x.setProtMemb( 0 );   // OK, uses public access function
   x.Display();
   y.setProtMemb( 5 );   // OK, uses public access function
   y.Display();
   // x.Protfunc();         error, Protfunc() is protected
   y.useProtfunc();      // OK, uses public access function
                        // in derived class
}
```

## <a name="see-also"></a>참고자료

[클래스 멤버에 대한 액세스 제어](member-access-control-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)