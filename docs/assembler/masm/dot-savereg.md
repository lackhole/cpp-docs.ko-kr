---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: cac7aa7f2bdbf6b60831d2beb062f86559ec0358
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178165"
---
# <a name="savereg"></a>.SAVEREG

생성 중 하나를 `UWOP_SAVE_NONVOL` 또는 `UWOP_SAVE_NONVOL_FAR` 지정 된 등록에 대 한 코드 항목을 해제 (`reg`) 오프셋 및 (`offset`) 현재 프롤로그 오프셋을 사용 하 여 합니다. MASM 가장 효율적인 인코딩 선택 합니다.

## <a name="syntax"></a>구문

> . SAVEREG reg 오프셋

## <a name="remarks"></a>설명

. SAVEREG ml64.exe 프레임 함수 해제 하는 방법을 지정할 수 있습니다 및에서 확장 하는 프롤로그 내 에서만 허용 됩니다 합니다 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 고 `.pdata`입니다. . 동작 스택이 없습니다을 실제로 구현 하는 지침 SAVEREG 보다 선행 되어야 합니다. 모두 해제 지시문 및 규약 확인 매크로에서 해제를 위한 코드를 래핑하는 것이 좋습니다.

자세한 내용은 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>