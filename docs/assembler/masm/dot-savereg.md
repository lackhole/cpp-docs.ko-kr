---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 324cf0e70a7ad619e5741c9acc18c24a72f54d13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397962"
---
# <a name="savereg"></a>.SAVEREG

현재 프롤로그 오프셋을 사용 하 여 지정 된 레지스터 (*reg*) 및 오프셋 (*오프셋*)에 대 한 `UWOP_SAVE_NONVOL` 또는 `UWOP_SAVE_NONVOL_FAR` 해제 코드 항목을 생성 합니다. MASM은 가장 효율적인 인코딩을 선택 합니다.

## <a name="syntax"></a>구문

> **. Savereg** *reg* __,__ *offset*

## <a name="remarks"></a>주의

**. SAVEREG**를 사용 하면 ml64.exe 사용자가 프레임 함수를 해제 하는 방법을 지정 하 고, 프롤로그 내 에서만 허용 되며,이를 [프로시저](../../assembler/masm/proc.md) 프레임 선언에서로 확장할 수 있습니다 [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문은 코드를 생성 하지 않습니다. `.xdata` 및 `.pdata`생성 합니다. **. SAVEREG** 는 해제할 작업을 실제로 구현 하는 명령 앞에와 야 합니다. 규약을 보장 하기 위해 매크로에서 해제할 해제 지시문과 코드를 모두 래핑하는 것이 좋습니다.

자세한 내용은 [x 64 용 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)
