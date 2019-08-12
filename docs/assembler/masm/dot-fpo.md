---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3bdb6af98aa71fef3d4af24091dc7463d917ce15
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915958"
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
프레임 유형을 나타냅니다.  자세한 내용은 [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-fpo_data) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>
