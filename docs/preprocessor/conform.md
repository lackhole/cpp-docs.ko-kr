---
title: 준수 pragma
ms.date: 08/29/2019
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: 816ff85bb19f549c6ea072073bd89fcd503545f2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220505"
---
# <a name="conform-pragma"></a>준수 pragma

**C++컴퓨터별**

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 컴파일러 옵션의 런타임 동작을 지정 합니다.

## <a name="syntax"></a>구문

> **#pragma 준수 (** *이름* [ **, 표시** ] [ **,** { **on** | **off** }] [[ **,** { **push** | **pop** }] [ **,** *식별자* [ **,** { **on** **off}** ]  |  ] ] **)**

### <a name="parameters"></a>매개 변수

*이름의*\
수정할 컴파일러 옵션의 이름을 지정합니다. 유일 하 게 유효한 이름은 `forScope`입니다.

**표시**\
필드 컴파일 중에 경고 메시지를 통해 *이름* (true 또는 false)의 현재 설정을 표시 합니다. `#pragma conform(forScope, show)` )을 입력합니다.

**켜기**, **끄기**\
필드 *Name* 을 **on** 으로 설정 하면 [/zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 컴파일러 옵션을 사용할 수 있습니다. 기본값은 **off**입니다.

**누르기**\
필드 *이름* 의 현재 값을 내부 컴파일러 스택에 푸시합니다. *Identifier*를 지정 하는 경우 *이름* 에 대 한 **on** 또는 **off** 값을 스택에 푸시할 지정할 수 있습니다. `#pragma conform(forScope, push, myname, on)` )을 입력합니다.

**창을**\
필드 *Name* 값을 내부 컴파일러 스택 맨 위의 값으로 설정 하 고 스택을 팝 합니다. 식별자가 **pop**에서 지정 된 경우에는 *식별자*가 포함 된 레코드를 찾을 때까지 스택이 다시 팝 됩니다. 스택의 다음 레코드에서 *이름* 에 대 한 현재 값이 *name*의 새 값이 됩니다. 스택의 레코드에 없는 *식별자* 를 사용 하 여 **pop** 를 지정 하는 경우 **pop** 는 무시 됩니다.

*한정자*\
필드 **Push** 또는 **pop** 명령에 포함할 수 있습니다. *Identifier* 를 사용 하는 경우 **on** 또는 **off** 지정자를 사용할 수도 있습니다.

## <a name="example"></a>예제

```cpp
// pragma_directive_conform.cpp
// compile with: /W1
// C4811 expected
#pragma conform(forScope, show)
#pragma conform(forScope, push, x, on)
#pragma conform(forScope, push, x1, off)
#pragma conform(forScope, push, x2, off)
#pragma conform(forScope, push, x3, off)
#pragma conform(forScope, show)
#pragma conform(forScope, pop, x1)
#pragma conform(forScope, show)

int main() {}
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
