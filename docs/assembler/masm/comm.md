---
title: COMM
ms.date: 08/30/2018
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: 342c8acd95fd45de1a21dc298325de9a7b40b717
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179109"
---
# <a name="comm"></a>COMM

에 지정 된 특성을 사용 하 여 빈약한 변수를 만듭니다 *정의*합니다.

## <a name="syntax"></a>구문

> **COMM** *정의* [합니다 *정의*]...

## <a name="remarks"></a>설명

공용 변수는 링커로 할당 되 고 초기화할 수 없습니다. 즉, 위치 또는 이러한 변수는 시퀀스에는 종속 될 수 없습니다.

각 *정의* 다음과 같은 형식을 갖습니다.

[*langtype*] [**NEAR** &#124; **FAR**] _label_**:**_type_[**:**_count_]

선택적 *langtype* 뒤에 오는 이름에 대 한 명명 규칙을 설정 합니다. 지정 된 모든 언어 재정의 **합니다. 모델** 지시문입니다. 선택적 **NEAR** 하거나 **극동** 현재 메모리 내 모델을 재정의 합니다. 합니다 *레이블* 변수의 이름입니다. *형식* 형식 지정자를 사용할 수 있습니다 ([바이트](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)등) 또는 바이트 수를 지정 하는 정수입니다. 선택적 *개수* ; 선언 된 데이터 개체의 요소 수를 지정 합니다. 기본값은 1입니다.

## <a name="example"></a>예제

이 예제에서는 512 바이트 요소의 배열을 만듭니다.

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>
