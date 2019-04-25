---
title: 인라인 어셈블리 최적화
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: d4956ba12e0bc268d78a895e6cb1ec6e2059262a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166882"
---
# <a name="optimizing-inline-assembly"></a>인라인 어셈블리 최적화

**Microsoft 전용**

함수에 `__asm` 블록이 있으면 여러 가지 방식으로 최적화에 영향을 받습니다. 먼저, 컴파일러는 `__asm` 블록 자체를 최적화하려고 하지 않습니다. 어셈블리 언어로 작성한 내용대로 결과가 발생합니다. 다음으로, `__asm` 블록이 있음으로 인해 레지스터 변수 저장에 영향을 줍니다. 컴파일러는 레지스터의 콘텐츠가 `__asm` 블록에 의해 변경될 경우 `__asm` 블록 전체에서 변수를 등록하지 않습니다. 마지막으로, 함수에 어셈블리 언어를 포함하면 일부 다른 함수 차원의 최적화에 영향을 줍니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[인라인 어셈블러](../../assembler/inline/inline-assembler.md)<br/>