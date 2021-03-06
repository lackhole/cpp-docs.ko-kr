---
title: vtordisp pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 3c676ab2bfee1b6cf3caff3ab456a4f23f2744c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216485"
---
# <a name="vtordisp-pragma"></a>vtordisp pragma

**C++컴퓨터별**

숨겨진 `vtordisp` 생성/소멸 치환 멤버의 추가를 제어 합니다.

## <a name="syntax"></a>구문

> **#pragma vtordisp (** [ **push,** ] *n* **)** \
> **pop (#pragma vtordisp)** \
> **#pragma vtordisp ()** \
> **#pragma vtordisp (** [ **push,** ] { **on** | **off** } **)**

### <a name="parameters"></a>매개 변수

**누르기**\
내부 컴파일러 스택에 `vtordisp` 현재 설정을 푸시하고 새 `vtordisp` 설정을 *n*으로 설정 합니다.  *N* 을 지정 하지 않으면 현재 `vtordisp` 설정이 변경 되지 않습니다.

**창을**\
내부 컴파일러 스택에서 상위 레코드를 제거 하 고 `vtordisp` 설정을 제거 된 값으로 복원 합니다.

*n*\
`vtordisp` 설정의 새 값을 지정 합니다. 가능한 값은 0, 1 또는 2 이며,, 및 `/vd0` `/vd2` 컴파일러 `/vd1`옵션에 해당 합니다. 자세한 내용은 [/vd (생성 치환 사용 안 함)](../build/reference/vd-disable-construction-displacements.md)를 참조 하세요.

**sign-on**\
`#pragma vtordisp(1)`와 같습니다.

**해제**\
`#pragma vtordisp(0)`와 같습니다.

## <a name="remarks"></a>설명

**Vtordisp** pragma는 가상 베이스를 사용 하는 코드에만 적용 됩니다. 파생 클래스가 가상 기본 클래스에서 상속된 가상 함수를 재정의하고 파생 클래스의 생성자 또는 소멸자가 가상 기본 클래스에 대한 포인터를 사용하여 해당 함수를 호출하는 경우, 컴파일러는 추가로 숨겨진 `vtordisp` 필드를 가상 기본 클래스에 사용할 수 있습니다.

**Vtordisp** pragma는 뒤에 오는 클래스의 레이아웃에 영향을 줍니다. , `/vd0` 및옵션`/vd2` 은 전체 모듈에 대해 동일한 동작을 지정 합니다. `/vd1` 0 또는 **off** 를 지정 하면 숨겨진 `vtordisp` 멤버가 표시 되지 않습니다. 클래스의 생성자 및 소멸자가 `this` 포인터가 가리키는 개체에 대해 가상 함수를 호출할 가능성이 없는 경우에만 vtordisp를 해제 합니다.

기본값인 1 또는 **on**을 지정 하면 필요한 경우 숨겨진 `vtordisp` 멤버를 사용할 수 있습니다.

2를 지정 하면 가상 `vtordisp` 함수를 사용 하는 모든 가상 기본에 대해 숨겨진 멤버를 사용할 수 있습니다.  `#pragma vtordisp(2)`부분적으로 생성 된 개체에 대해 **dynamic_cast** 의 올바른 성능을 보장 하기 위해 필요할 수 있습니다. 자세한 내용은 [컴파일러 경고 (수준 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)를 참조 하세요.

`#pragma vtordisp()`인수 없이는 `vtordisp` 설정을 초기 설정으로 복원 합니다.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
