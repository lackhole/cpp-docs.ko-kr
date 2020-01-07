---
title: ALIGN (MASM)
ms.date: 12/17/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: 700721768deaf92e88b32a97e68c6e017219d19d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316592"
---
# <a name="align"></a>ALIGN

**ALIGN** 지시문은 해당 매개 변수의 배수 인 주소에 다음 데이터 요소 또는 명령을 맞춥니다. 매개 변수는 세그먼트 맞춤 보다 작거나 같은 2의 거듭제곱 이어야 합니다 (예: 1, 2, 4 등).

## <a name="syntax"></a>구문

> ⟦*ConstantExpression*⟧ **맞추기**

## <a name="remarks"></a>주의

**ALIGN** 지시어를 사용 하면 데이터 요소 또는 명령의 시작 오프셋을 지정할 수 있습니다. 데이터 요소 사이에 공간이 낭비 되는 경우 데이터를 정렬 하면 성능을 향상 시킬 수 있습니다. 데이터 액세스가 캐시 선 내에 적합 한 경계에 있는 경우 성능이 크게 향상 될 수 있습니다. 네이티브 형식에 대 한 자연 경계의 액세스는 내부 하드웨어 재정렬 마이크로코드에 소요 되는 시간을 의미 합니다.

정렬 된 지침은 주로 플랫 주소 지정 모델을 사용 하는 최신 프로세서에서 드물게 발생 하지만 다른 주소 지정 모델의 경우 이전 코드의 점프 대상에 필요할 수 있습니다.

데이터를 정렬할 때 건너뛴 공간은 0으로 채워집니다. 지침이 정렬 되 면 건너뛴 공간이 적절 한 크기의 NOP 명령으로 채워집니다.

## <a name="see-also"></a>참조

[심지어](even.md)\
[지시문 참조](directives-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
