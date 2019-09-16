---
title: 링커 도구 오류 LNK1352
description: 링커 도구 오류 LNK1352은 지원 되지 않는 섹션 병합이 시도 될 때 발생 합니다.
ms.date: 09/10/2019
f1_keywords:
- LNK1352
helpviewer_keywords:
- LNK1352
ms.openlocfilehash: 38f773bfd669529dfb1ada9c7bb59e6f0962c9c7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908395"
---
# <a name="linker-tools-error-lnk1352"></a>링커 도구 오류 LNK1352

> '*section_name_1*' 및 '*section_name_2*'는 다른 섹션으로 병합할 수 없습니다.

## <a name="remarks"></a>설명

*Section_name_1* 및 *section_name_2* 을 동일한 섹션에 병합 해야 하므로 링커가 허용 되지 않는 섹션 병합을 발견 했습니다. 예를 들어 링커가 `.stls` 섹션과 `.tls` 섹션을 다른 섹션으로 병합 하려는 시도를 감지 하는 경우이 오류가 발생 합니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

이 문제에 대 한 링커 명령줄에서 [/merge](../../build/reference/merge-combine-sections.md) 옵션을 선택 합니다.

## <a name="see-also"></a>참고자료

[링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
