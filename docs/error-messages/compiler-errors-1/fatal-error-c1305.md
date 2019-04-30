---
title: 심각한 오류 C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 988842a0d5e8002ffd1478a2e10a8c88ee971911
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397499"
---
# <a name="fatal-error-c1305"></a>심각한 오류 C1305

'pgd_file' 프로필 데이터베이스는 다른 아키텍처용입니다.

다른 플랫폼에 전달 된에 대 한 /ltcg: pginstrument 작업에서 생성 된.pgd 파일로 [/ltcg: pgoptimize](../../build/reference/ltcg-link-time-code-generation.md) 합니다. [프로필 기반 최적화](../../build/profile-guided-optimizations.md) x86 및 x64 플랫폼에 사용할 수 있습니다. 그러나 단일 플랫폼에 대 한 /ltcg: pginstrument 작업과 생성 된.pgd 파일을 올바르지 다른 플랫폼에 대 한 /ltcg: pgoptimize 입력으로 합니다.

이 오류를 해결 하려면만 동일한 플랫폼에서 /ltcg: pgoptimize /ltcg: pginstrument를 사용 하 여 만든.pgd 파일을 전달 합니다.