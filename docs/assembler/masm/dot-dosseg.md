---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 17edea122afc03a8c3a2fdc86ee6c06c2ccf3c85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398484"
---
# <a name="dosseg-32-bit-masm"></a>. .DOSSEG (32 비트 MASM)

MS-DOS 세그먼트 규칙에 따라 세그먼트를 정렬 합니다. CODE first, DGROUP에 없는 세그먼트, DGROUP의 세그먼트 순서로 정렬 합니다. (32 비트 MASM에만 해당)

## <a name="syntax"></a>구문

> **.DOSSEG**

## <a name="remarks"></a>주의

D 그룹의 세그먼트는 다음 순서를 따릅니다. 즉, BSS 나 스택에 있지 않은 세그먼트, BSS 세그먼트 및 finally STACK 세그먼트가 있습니다. 주로 MASM 독립 실행형 프로그램에서 CodeView 지원을 보장 하는 데 사용 됩니다. [.Dosseg](../../assembler/masm/dosseg.md)와 동일 합니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](../../assembler/masm/directives-reference.md)
