---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 2b91698640e028bf91d822c12b85ded651a04d8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203066"
---
# <a name="if-masm"></a>IF (MASM)

어셈블리의 부여 *ifstatements* 하는 경우 *expression1* 가 true (0이 아닌) 또는 *elseifstatements* 경우 *expression1* 이 false (0) 및 *expression2* 그렇습니다.

## <a name="syntax"></a>구문

> IF *expression1*<br/>
> *ifstatements*<br/>
> [[ELSEIF *expression2*<br/>
> *elseifstatements*]]<br/>
> [[ELSE<br/>
> *elsestatements*]]<br/>
> ENDIF

## <a name="remarks"></a>설명

다음 지시문 대신 사용할 수 있습니다 [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**를 **ELSEIFDIF**를 **ELSEIFDIFI**를 **ELSEIFE**, **ELSEIFIDN**하십시오 **ELSEIFIDNI**, **ELSEIFNB**, 및 **ELSEIFNDEF**. 필요에 따라 조합 *elsestatements* 이전 식이 false 인 경우. 어셈블리 타임 식 계산 되는 참고 합니다.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>