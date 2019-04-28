---
title: 상속(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
ms.openlocfilehash: 0180a2f7b41e3169bc9e25d8b598dbe2b84be088
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184582"
---
# <a name="inheritance--c"></a>상속(C++)

이 단원에서는 파생 클래스를 사용하여 확장 가능한 프로그램을 생성하는 방법을 설명합니다.

## <a name="overview"></a>개요

"상속" 이라는 메커니즘을 사용 하 여 기존 클래스에서 새 클래스를 파생 될 수 있습니다 (시작 하는 정보를 참조 하세요 [단일 상속](../cpp/single-inheritance.md)). 파생에 사용되는 클래스를 특정 파생 클래스의 "기본 클래스"라고 합니다. 파생 클래스는 다음 구문을 사용하여 선언됩니다.

```cpp
class Derived : [virtual] [access-specifier] Base
{
   // member list
};
class Derived : [virtual] [access-specifier] Base1,
   [virtual] [access-specifier] Base2, . . .
{
   // member list
};
```

클래스에 대한 태그(이름) 뒤에 콜론과 기본 사양 목록이 나타납니다.  그렇게 명명된 기본 클래스는 이전에 선언되어 있어야 합니다.  기본 사양은 키워드 중 하나인 액세스 지정자를 포함할 수 있습니다 **공개**를 **보호** 하거나 **개인**합니다.  이러한 액세스 지정자는 기본 클래스 이름 앞에 나타나고 해당 기본 클래스에만 적용됩니다.  이러한 지정자는 기본 클래스의 멤버를 사용할 수 있는 파생 클래스의 권한을 제어합니다.  참조 [멤버 Access Control](../cpp/member-access-control-cpp.md) 기본 클래스 멤버에 대 한 액세스에 대 한 정보에 대 한 합니다.  액세스 지정자를 생략 하면 해당 자료에 대 한 액세스 비율은 **개인**합니다.  기본 사양은 키워드를 포함할 수 있습니다 **가상** 가상 상속을 나타냅니다.  이 키워드는 액세스 지정자(있는 경우) 앞이나 뒤에 나타날 수 있습니다.  가상 상속을 사용하는 경우 기본 클래스를 가상 기본 클래스라고 합니다.

여러 기본 클래스를 쉼표로 구분하여 지정할 수 있습니다.  상속 모델은 단일 기본 클래스를 지정 하면 [단일 상속](../cpp/single-inheritance.md)합니다. 둘 이상의 기본 클래스를 지정 하는 경우 상속 모델 이라고 [다중 상속](../cpp/multiple-base-classes.md)합니다.

주제는 다음과 같습니다.

- [단일 상속](../cpp/single-inheritance.md)

- [다중 기본 클래스](../cpp/multiple-base-classes.md)

- [가상 함수](../cpp/virtual-functions.md)

- [명시적 재정](../cpp/explicit-overrides-cpp.md)

- [추상 클래스](../cpp/abstract-classes-cpp.md)

- [범위 규칙 요약](../cpp/summary-of-scope-rules.md)

합니다 [__super](../cpp/super.md) 하 고 [__interface](../cpp/interface.md) 키워드가이 섹션에 설명 되어 있습니다.

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)