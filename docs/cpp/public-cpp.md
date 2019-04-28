---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: 24cc4dd3cd7e0c893664339e7ad83383839b0b11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244478"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>구문

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>설명

목록 앞에 오는 클래스 멤버를 **공용** 키워드 해당 멤버 함수에서 액세스할 수 있도록 지정 합니다. 이 설정은 다음 액세스 지정자 또는 클래스 끝까지 선언된 모든 멤버에 적용됩니다.

이름 앞에 오는 기본 클래스의는 **공용** 키워드 지정 기본 클래스의 public 및 protected 멤버는 공용 파생된 클래스의 멤버를 각각 보호 합니다.

클래스에서 멤버의 기본 액세스는 전용입니다. 구조체나 공용 구조체에서 멤버의 기본 액세스는 공용입니다.

기본 클래스의 기본 액세스는 클래스에 대해 전용이고 구조체에 대해 공용입니다. 공용 구조체에 기본 클래스를 사용할 수 없습니다.

자세한 내용은 참조 하세요. [사설](../cpp/private-cpp.md), [보호](../cpp/protected-cpp.md)를 [friend](../cpp/friend-cpp.md), 및 멤버 액세스 테이블 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) .

## <a name="clr-specific"></a>/clr 관련

CLR 형식에는 C++ 액세스 지정자 키워드 (**공용**를 **개인**, 및 **보호**) 형식 및 어셈블리와 관련 된 메서드 표시 여부에 영향을 줄 수 있습니다. 자세한 내용은 [멤버 Access Control](member-access-control-cpp.md)합니다.

> [!NOTE]
>  파일을 컴파일하면 [/LN](../build/reference/ln-create-msil-module.md) 이 동작의 영향을 받지 않습니다. 이 경우 관리되는 클래스(공용 또는 전용)가 모두 표시됩니다.

## <a name="end-clr-specific"></a>END /clr 관련

## <a name="example"></a>예제

```cpp
// keyword_public.cpp
class BaseClass {
public:
   int pubFunc() { return 0; }
};

class DerivedClass : public BaseClass {};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   aBase.pubFunc();       // pubFunc() is accessible
                          //    from any function
   aDerived.pubFunc();    // pubFunc() is still public in
                          //    derived class
}
```

## <a name="see-also"></a>참고자료

[클래스 멤버에 대한 액세스 제어](member-access-control-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)