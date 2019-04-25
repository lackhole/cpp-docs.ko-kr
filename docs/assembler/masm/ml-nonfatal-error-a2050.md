---
title: ML 심각하지 않은 오류 A2050
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 59d08b9c2743a3b45633527bcc54b3e1c4d6a58c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62177554"
---
# <a name="ml-nonfatal-error-a2050"></a>ML 심각하지 않은 오류 A2050

**실시간 또는 BCD 수 없습니다**

부동 소수점 (실수) 또는 binary coded decimal (BCD) 상수를 사용한 이외의 데이터 이니셜라이저로 합니다.

다음 중 하나에 다음이 발생 했습니다.

- 실수 또는 BCD를 식에서 사용 되었습니다.

- 실수를 초기화 하는 데 지시문 이외의 [DWORD](../../assembler/masm/dword.md)를 [QWORD](../../assembler/masm/qword.md), 또는 [TBYTE](../../assembler/masm/tbyte.md)합니다.

- BCD를 초기화 하는 데 지시문 이외의 `TBYTE`합니다.

## <a name="see-also"></a>참고자료

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>