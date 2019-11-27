---
title: COMM
ms.date: 08/30/2018
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: d36161ba54ca80fc0f576c6f0a7c2a9410bf8075
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541029"
---
# <a name="comm"></a>COMM

*정의*에 지정 된 특성을 사용 하 여 communal 변수를 만듭니다.

## <a name="syntax"></a>구문

> **통신** *정의* ⟦ __,__ *정의* ... ⟧

## <a name="remarks"></a>주의

Communal 변수는 링커에 의해 할당 되며 초기화할 수 없습니다. 즉, 이러한 변수의 위치 또는 시퀀스에 의존할 수 없습니다.

각 *정의* 의 형식은 다음과 같습니다.

⟦ *⟧* ⟦**NEAR** | **FAR**⟧ _label_ **:** _type_⟦ **:** _count_⟧

선택적 *언어 유형* 은 뒤에 오는 이름에 대 한 명명 규칙을 설정 합니다. 에서 지정 된 모든 언어를 재정의 **합니다. 모델** 지시문입니다. 선택 사항인 **NEAR** 또는 **FAR** 는 현재 메모리 모델을 재정의 합니다. *레이블은* 변수의 이름입니다. *형식은* 모든 형식 지정자 ([BYTE](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)등) 이거나 바이트 수를 지정 하는 정수일 수 있습니다. 선택적 *개수* 는 선언 된 데이터 개체의 요소 수를 지정 합니다. 기본 *카운트* 는 1입니다.

## <a name="example"></a>예제

이 예제에서는 512 바이트 요소로 이루어진 배열을 만듭니다.

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>참조

[지시문 참조](directives-reference.md)
