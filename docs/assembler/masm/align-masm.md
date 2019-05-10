---
title: ALIGN (MASM)
ms.date: 01/02/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: eb42b1952b3fd59438f0dd4c29d48c91c4d8864d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166479"
---
# <a name="align-masm"></a>ALIGN (MASM)

합니다 **ALIGN** 지시문 다음 데이터 요소 또는 해당 매개 변수의 배수인 주소에는 명령에 맞춥니다. 매개 변수 2의 거듭제곱 이어야 합니다 (예: 1, 2, 4, 및 등)는 보다 작거나 세그먼트 맞춤 합니다.

## <a name="syntax"></a>구문

> ALIGN [[*number*]]

## <a name="remarks"></a>설명

합니다 **ALIGN** 지시문을 사용 하면 데이터 요소 또는 명령의의 시작 오프셋을 지정할 수 있습니다. 정렬 된 데이터는 데이터 요소 사이 불필요 하 게 공백 희생 성능을 개선할 수 있습니다. 캐시 라인 내에 맞는 경계에 데이터 액세스의 경우 성능이 크게 향상을 볼 수 있습니다. 네이티브 형식에 대 한 자연 경계에 대 한 액세스는 내부 하드웨어 재정렬 마이크로코드에 소요 된 시간을 의미 합니다.

정렬 된 지침에 대 한 필요성은 플랫 주소 지정 모델을 사용 하지만 다른 주소 지정 모델에 대 한 이전 코드에서 점프 대상에 필요할 수 있습니다 최신 프로세서에서 드물게 나타납니다.

데이터 aligned 인 경우 건너뛴된 공간을 0으로 채워집니다. 지침, 맞춰진 경우 건너뛴된 공간 크기가 적절 하 게 NOP 지침으로 채워집니다.

## <a name="see-also"></a>참고자료

[EVEN](even.md)<br/>
[지시문 참조](../../assembler/masm/directives-reference.md)<br/>