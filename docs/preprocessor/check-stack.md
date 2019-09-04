---
title: check_stack pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 4c976692ec36cedcb73825ee0cc7093736a3a3dc
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216130"
---
# <a name="check_stack-pragma"></a>check_stack pragma

**해제** (또는 **-** )가 지정 된 경우 스택 프로브를 해제 하거나 **on** (또는 **+** )이 지정 된 경우 스택 프로브를 설정 하도록 컴파일러에 지시 합니다.

## <a name="syntax"></a>구문

> **#pragma check_stack (** [{ **on** | **off** }] **)** \
> **#pragma check_stack** { **+**  |  **-** }

## <a name="remarks"></a>설명

이 pragma는 pragma가 표시된 후 정의된 첫 번째 함수에서 적용됩니다. 스택 프로브는 인라인으로 생성된 함수의 일부나 매크로의 일부가 아닙니다.

**Check_stack** pragma에 대 한 인수를 지정 하지 않으면 스택 검사가 명령줄에 지정 된 동작으로 되돌아갑니다. 자세한 내용은 [컴파일러 옵션](../build/reference/compiler-options.md)을 참조하세요. `#pragma check_stack` 및 [/gs](../build/reference/gs-control-stack-checking-calls.md) 옵션의 상호 작용은 다음 표에 요약 되어 있습니다.

### <a name="using-the-check_stack-pragma"></a>check_stack Pragma 사용

|구문|/Gs 옵션을 사용한<br /><br /> 컴파일 여부|동작|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` 또는<br /><br /> `#pragma check_stack`|예|뒤에 오는 함수에 대한 스택 검사 해제|
|`#pragma check_stack( )` 또는<br /><br /> `#pragma check_stack`|아니요|뒤에 오는 함수에 대한 스택 검사 설정|
|`#pragma check_stack(on)`<br /><br /> 디스크나`#pragma check_stack +`|Yes 또는 No|뒤에 오는 함수에 대한 스택 검사 설정|
|`#pragma check_stack(off)`<br /><br /> 디스크나`#pragma check_stack -`|Yes 또는 No|뒤에 오는 함수에 대한 스택 검사 해제|

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
