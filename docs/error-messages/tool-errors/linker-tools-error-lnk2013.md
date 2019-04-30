---
title: 링커 도구 오류 LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 4d932a89f1b0bde27f6de2f84b2ed103dab1b1b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299070"
---
# <a name="linker-tools-error-lnk2013"></a>링커 도구 오류 LNK2013

픽스업 형식 픽스업 오버플로입니다. 'Symbol name' 대상 범위를 벗어났습니다.

링커가 필요한 주소 또는 offset에 맞지 지정 된 명령 대상 기호 명령 위치에서 너무 멀리 떨어져 있으므로.

에 사용 하 여 여러 이미지를 만들어서이 문제를 해결할 수는 [/order](../../build/reference/order-put-functions-in-order.md) 명령 및 대상에 좀 더 근접 하므로 옵션입니다.

기호 이름은 사용자 정의 기호 (및 컴파일러에서 생성 된 기호가 아닙니다) 오류를 해결 하려면 다음 작업을 시도해 볼 수 있습니다.

- 비정적 되도록 정적 함수를 변경 합니다.

- 호출자와 동일 하도록 정적 함수를 포함 하는 코드 섹션을 이름을 바꿉니다.

사용 하 여 `DUMPBIN /SYMBOLS`, 정적 함수 인지 확인 합니다.