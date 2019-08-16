---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: b793b3efa72a676b800c10b98ea06001ddcf10d5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491431"
---
# <a name="fpo"></a>.FPO

여. FPO 지시문은 디버그 레코드를 debug $ F 세그먼트 또는 섹션으로 내보내기를 제어 합니다.

## <a name="syntax"></a>구문

> FPO (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*, *cbFrame*)

### <a name="parameters"></a>매개 변수

*cdwLocals*<br/>
지역 변수의 수 이며, 부호 없는 32 비트 값입니다.

*cdwParams*<br/>
DWORD에서 부호 없는 16 비트 값인 매개 변수의 크기입니다.

*cbProlog*<br/>
부호 없는 8 비트 값인 함수 프롤로그 코드의 바이트 수입니다.

*cbRegs*<br/>
숫자 레지스터가 저장 되었습니다.

*fUseBP*<br/>
EBP 레지스터가 할당 되었는지 여부를 나타냅니다. 0 또는 1입니다.

*cbFrame*<br/>
프레임 유형을 나타냅니다.  자세한 내용은 [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>
