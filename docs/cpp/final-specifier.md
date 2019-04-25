---
title: final 지정자
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: c6400c8060664713fdd004a5aa9536e0617bc0c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154778"
---
# <a name="final-specifier"></a>final 지정자

**final** 키워드를 사용하여 파생 클래스에서 재정의할 수 없는 가상 함수를 지정할 수 있습니다. 상속할 수 없는 클래스를 지정하기 위해 해당 키워드를 사용할 수도 있습니다.

## <a name="syntax"></a>구문

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>설명

**final**은 상황에 따라 다르며 함수 선언 또는 클래스 이름 뒤에 사용할 때만 특별한 의미를 갖습니다. 그렇지 않으면 예약된 키워드가 아닙니다.

**final**이 클래스 선언에 사용되는 경우 `base-classes`는 선언의 선택적 부분입니다.

## <a name="example"></a>예제

다음 예제는 **final** 키워드를 사용하여 가상 함수를 재정의할 수 없음을 지정합니다.

```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // compiler error: attempting to
                         // override a final function
};
```

멤버 함수를 재정의할 수 있음을 지정하는 방법에 대한 자세한 내용은 [override 지정자](../cpp/override-specifier.md)를 참조하세요.

다음 예제는 **final** 키워드를 사용하여 클래스를 상속할 수 없음을 지정합니다.

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>참고 항목

[키워드(C++)](../cpp/keywords-cpp.md)<br/>
[override 지정자](../cpp/override-specifier.md)