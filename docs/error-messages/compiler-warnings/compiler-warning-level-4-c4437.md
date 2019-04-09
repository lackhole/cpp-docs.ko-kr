---
title: 컴파일러 경고(수준 4) C4437
ms.date: 11/04/2016
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
ms.openlocfilehash: 9ff52ae6d10f7d4ba429bbf3457a2a6b969998d4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037821"
---
# <a name="compiler-warning-level-4-c4437"></a>컴파일러 경고(수준 4) C4437

'class2' 가상 기본 'class1' 사이의 dynamic_cast가 일부 컨텍스트에서 실패할 컴파일/vd2 사용해 하거나 적용 'class2' #pragma vtordisp(2) 사용 하 여 정의할 수 없습니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

컴파일러에서 다음과 같은 특성의 `dynamic_cast` 작업이 발견되었습니다.

- 캐스트는 기본 클래스 포인터에서 파생된 클래스 포인터의 방향으로 수행됩니다.

- 파생된 클래스는 기본 클래스를 상속합니다.

- 파생된 클래스에는 가상 기본에 대한 `vtordisp` 필드가 포함되지 않습니다.

- 캐스팅 생성자 또는 파생된 클래스의 소멸자가 없거나 더 몇 가지 클래스 (이 고, 그렇지 컴파일러 경고 C4436 발생 하는) 파생된 클래스에서 상속 합니다.

경고 나타냅니다는 `dynamic_cast` 부분적으로 생성 된 개체에서 작동 하는 경우 제대로 수행 되지 않을 수 있습니다.  이 경우에는 바깥쪽 함수 생성자 또는 경고에 지정 된 파생된 클래스를 상속 하는 클래스의 소멸자에서 호출 될 때 발생 합니다.  경고에 지정 된 파생된 클래스를 더 이상 파생 또는 바깥쪽 함수 개체 생성 이나 소멸 중에 호출 되지, 경고를 무시할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C4437를 생성 하 고 누락 된에서 발생 하는 코드 생성 문제를 보여 줍니다 `vtordisp` 필드입니다.

```cpp
// C4437.cpp
// To see the warning and runtime assert, compile with: /W4
// To eliminate the warning and assert, compile with: /W4 /vd2
//       or compile with: /W4 /DFIX
#pragma warning(default : 4437)
#include <cassert>

struct A
{
public:
    virtual ~A() {}
};

#if defined(FIX)
#pragma vtordisp(push, 2)
#endif
struct B : virtual A
{
    B()
    {
        func();
    }

    void func()
    {
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4437
        assert(this == b);              // assert unless compiled with /vd2
    }
};
#if defined(FIX)
#pragma vtordisp(pop)
#endif

struct C : B
{
    int i;
};

int main()
{
    C c;
}
```

## <a name="see-also"></a>참고자료

[dynamic_cast 연산자](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[컴파일러 경고(수준 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)