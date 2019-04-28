---
title: .DOSSEG
ms.date: 08/30/2018
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 28b3e351030ee83693c0fec5568aacf9b4b77c27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204363"
---
# <a name="dosseg"></a>.DOSSEG

MS-DOS 세그먼트 규칙에 따라 세그먼트를 정렬 합니다. 먼저 다음 없는 DGROUP, 세그먼트 및 코드 다음 DGROUP 세그먼트 합니다.

## <a name="syntax"></a>구문

> .DOSSEG

## <a name="remarks"></a>설명

DGROUP 세그먼트가이 순서를 따릅니다: BSS 또는 스택에 없는 세그먼트 BSS 세그먼트 및 스택 세그먼트입니다. 독립 실행형 프로그램 MASM의에서 CodeView 지원 되도록 하기 위해 주로 사용 됩니다. 동일 [DOSSEG](../../assembler/masm/dosseg.md)합니다.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>