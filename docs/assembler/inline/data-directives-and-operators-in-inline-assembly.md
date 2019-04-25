---
title: 인라인 어셈블리의 데이터 지시문과 연산자
ms.date: 08/30/2018
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
ms.openlocfilehash: 52e20c37f3066122a062e3fc9c64ced576b6c302
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167233"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>인라인 어셈블리의 데이터 지시문과 연산자

**Microsoft 전용**

`__asm` 블록은 C 또는 C++ 데이터 형식과 개체를 참조할 수 있지만 MASM 지시문이나 연산자를 사용하여 데이터 개체를 정의할 수 없습니다. 정의 지시문을 구체적으로 사용할 수 없습니다 **DB**, `DW`, **DD**, `DQ`, `DT`, 및 `DF`, 또는 연산자 `DUP` 또는 **이**합니다. MASM 구조체와 레코드도 사용할 수 없습니다. 인라인 어셈블러 지시문을 허용 하지 않습니다 `STRUC`, `RECORD`를 **너비**, 또는 **마스크**합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>