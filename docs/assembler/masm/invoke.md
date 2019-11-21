---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: 853bc9cd22d866357a4cd2d695beccc3efc20acf
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703966"
---
# <a name="invoke-32-bit-masm"></a>INVOKE (32 비트 MASM)

*식*으로 지정 된 주소에서 프로시저를 호출 하 여 언어 형식의 표준 호출 규칙에 따라 스택에서 인수를 전달 하거나 레지스터에 프로시저를 전달 합니다. (32 비트 MASM에만 해당)

## <a name="syntax"></a>구문

> 호출 *식* [[, *arguments*]]

## <a name="remarks"></a>주의

프로시저에 전달 되는 각 인수는 식, 레지스터 쌍 또는 주소 식 (`ADDR`뒤에 오는 식) 일 수 있습니다.

## <a name="see-also"></a>참조

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>