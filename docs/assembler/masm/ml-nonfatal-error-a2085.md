---
title: ML 심각하지 않은 오류 A2085
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 3bd89fb2b7f8b755cdb095e63ed89386332ecf9d
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855760"
---
# <a name="ml-nonfatal-error-a2085"></a>ML 심각하지 않은 오류 A2085

**명령 또는 레지스터가 현재 CPU 모드에서 허용 되지 않습니다.**

현재 프로세서 모드에 대해 유효 하지 않은 명령, 레지스터 또는 키워드를 사용 하려고 한 경우

예를 들어 32 비트 레지스터에는 [386](../../assembler/masm/dot-386.md) 이상이 필요 합니다. CR0 레지스터와 같은 컨트롤 레지스터에는 특권 모드 [. 386p](../../assembler/masm/dot-386p.md) 이상이 필요 합니다. 이 오류는를 필요로 하는 **NEAR32**, **FAR32**및 **FLAT** 키워드에 대해서도 생성 됩니다. **386** 이상.

## <a name="see-also"></a>참조

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>