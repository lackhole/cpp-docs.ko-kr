---
title: vtordisp
ms.date: 10/18/2018
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 67c6c329bcee75012f6075334760925eca945501
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034380"
---
# <a name="vtordisp"></a>vtordisp

**C++ 전용**

숨겨진 vtordisp 생성/소멸 치환 멤버의 추가를 제어합니다.

## <a name="syntax"></a>구문

```cpp
#pragma vtordisp([push,] n)
#pragma vtordisp(pop)
#pragma vtordisp()
#pragma vtordisp([push,] {on | off})
```

### <a name="parameters"></a>매개 변수

*push*<br/>
내부 컴파일러 스택에 현재 vtordisp 설정을 푸시하고 새 vtordisp 설정이 설정 되어 *n*합니다.  하는 경우 *n* 지정 하지 않으면 현재 vtordisp 설정이 변경 되지 않습니다.

*pop*<br/>
내부 컴파일러 스택에서 상위 레코드를 제거하고 vtordisp 설정을 제거된 값으로 복원합니다.

*n*<br/>
Vtordisp 설정에 대해 새 값을 지정합니다. 가능한 값은 0, 1 또는 2에 해당 하는 `/vd0`, `/vd1`, 및 `/vd2` 컴파일러 옵션입니다. 자세한 내용은 [/vd (생성 치환 사용 안 함)](../build/reference/vd-disable-construction-displacements.md)합니다.

*On*<br/>
`#pragma vtordisp(1)`와 같습니다.

*해제*<br/>
`#pragma vtordisp(0)`와 같습니다.

## <a name="remarks"></a>설명

합니다 **vtordisp** pragma 가상 기본을 사용 하는 코드에만 적용 됩니다. 파생된 클래스가 가상 기본 클래스에서 상속 하는 가상 함수를 재정의 하 고 컴파일러가 추가 숨겨진된 발생할수있습니다생성자나파생된클래스의소멸자를가상기본클래스에대한포인터를사용하여해당함수를호출하는경우**vtordisp** 필드를 가상 기본 클래스입니다.

합니다 **vtordisp** pragma 그 뒤에 나오는 클래스의 레이아웃에 영향을 줍니다. 합니다 `/vd0`, `/vd1`, 및 `/vd2` 옵션 전체 모듈에 대 한 동일한 동작을 지정 합니다. 0을 지정 하거나 *해제* 숨겨진를 표시 하지 않습니다 **vtordisp** 멤버입니다. 해제할 **vtordisp** 클래스의 생성자 및 소멸자 호출 가상 가능성이 없는 함수에서 가리키는 개체에 없는 경우에 합니다 **이** 포인터입니다.

1을 지정 또는 *에*, 숨겨진 기본값을 사용 하도록 설정 **vtordisp** 멤버는 필요 합니다.

2는 숨겨진 설정 지정 **vtordisp** 가상 함수를 사용 하 여 모든 가상 기본의 멤버입니다.  `vtordisp(2)` 올바른 성능을 보장 하기 위해 해야 할 수도 있습니다 **dynamic_cast** 부분적으로 생성 된 개체입니다. 자세한 내용은 [컴파일러 경고 (수준 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)합니다.

`#pragma vtordisp()`를 인수 없이 vtordisp 설정이 초기 설정으로 복원 합니다.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**C++ 전용 종료**

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)