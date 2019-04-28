---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 83d6e81ea7dd35038f27f2721f3cc41fe49ef1bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204060"
---
# <a name="fpo"></a>.FPO

합니다. FPO 지시문 디버그 레코드를.debug$ F 세그먼트 또는 섹션의 내보내기가 제어합니다.

## <a name="syntax"></a>구문

> FPO (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*, *cbFrame*)

### <a name="parameters"></a>매개 변수

*cdwLocals*<br/>
지역 변수는 부호 없는 32 비트 값의 수입니다.

*cdwParams*<br/>
DWORD, 부호 없는 16 비트 값을 매개 변수 크기입니다.

*cbProlog*<br/>
함수 프롤로그 코드에서 부호 없는 8 비트 값을 바이트 수입니다.

*cbRegs*<br/>
저장 된 레지스터 번호입니다.

*fUseBP*<br/>
EBP 레지스터에 할당 되어 있는지 여부를 나타냅니다. 0 또는 1입니다.

*cbFrame*<br/>
프레임 유형을 나타냅니다.  참조 [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data) 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>