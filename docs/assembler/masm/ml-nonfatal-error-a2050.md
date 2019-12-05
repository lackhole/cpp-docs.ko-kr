---
title: ML 심각하지 않은 오류 A2050
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 15c6449ff4207c92dee28120d4f61be641cf01c8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856579"
---
# <a name="ml-nonfatal-error-a2050"></a>ML 심각하지 않은 오류 A2050

**실수 또는 BCD 숫자가 허용 되지 않습니다.**

부동 소수점 (실수) 숫자 또는 BCD (binary 코딩 된 10 진수) 상수가 데이터 이니셜라이저가 아닌 다른 방식으로 사용 되었습니다.

다음 중 하나가 발생 했습니다.

- 식에 실수 또는 BCD가 사용 되었습니다.

- 실수를 사용 하 여 [DWORD](../../assembler/masm/dword.md), [qword(64](../../assembler/masm/qword.md)또는 [1tb](../../assembler/masm/tbyte.md)이외의 지시어를 초기화 했습니다.

- BCD가 `TBYTE`이외의 지시어를 초기화 하는 데 사용 되었습니다.

## <a name="see-also"></a>참조

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>