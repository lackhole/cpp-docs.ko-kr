---
title: 인라인 어셈블리의 세그먼트 참조
ms.date: 08/30/2018
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
ms.openlocfilehash: 5c07fa897da23a55f376a20e7588c8c8c269d1a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167376"
---
# <a name="segment-references-in-inline-assembly"></a>인라인 어셈블리의 세그먼트 참조

**Microsoft 전용**

이름 대신 레지스터로 세그먼트를 참조해야 합니다. 예를 들어 세그먼트 이름 `_TEXT`는 올바르지 않습니다. 세그먼트 재정의에서는 ES:[BX]와 같이 레지스터를 명시적으로 사용해야 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>