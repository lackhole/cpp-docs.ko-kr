---
title: 링커 도구 오류 LNK1120
description: 링크에서 확인 되지 않은 외부 기호 오류의 수를 보고 하는 LNK1120 링커 오류에 대해 설명 합니다.
ms.date: 10/31/2019
f1_keywords:
- LNK1120
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
ms.openlocfilehash: 21a1ede07a69cdc065dd897715e243115529600d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626576"
---
# <a name="linker-tools-error-lnk1120"></a>링커 도구 오류 LNK1120

> 확인 되지 않은 외부 *수*

오류 LNK1120 현재 링크에서 확인 되지 [않은 외부 기호](linker-tools-error-lnk2001.md#what-is-an-unresolved-external-symbol) 오류 수를 보고 합니다.

확인 되지 않은 각 외부 기호는 먼저 [LNK2001](linker-tools-error-lnk2001.md) 또는 [LNK2019](linker-tools-error-lnk2019.md) 오류로 보고 됩니다. LNK1120 메시지는 마지막으로 제공 되며 확인 되지 않은 기호 오류 수를 표시 합니다.

> [!IMPORTANT]
> **이 오류는 해결할 필요가 없습니다.** 이 오류는 빌드 출력에 앞서 모든 LNK2001 및 LNK2019 링커 오류를 수정할 때 사라집니다. 항상 첫 번째 보고 된 오류에서 시작 하 여 문제를 해결 합니다. 이후 오류는 이전에 발생 한 오류 때문일 수 있습니다.
