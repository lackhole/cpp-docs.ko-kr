---
title: 어셈블리 언어 설명
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: fc37658eccd99b61d45aa9a9a7a2675ef90eee89
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167246"
---
# <a name="assembly-language-comments"></a>어셈블리 언어 설명

**Microsoft 전용**

`__asm` 블록의 지침에서는 어셈블리 언어 주석을 사용할 수 있습니다.

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C 매크로가 단일 논리 줄로 확장되기 때문에 매크로에서 어셈블리 언어 주석을 사용하지 마십시오. (참조 [C 매크로로 __asm 블록 정의](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) `__asm` 블록 수도 C-스타일 주석도 포함할; 자세한 내용은 참조 하십시오 [C를 사용 하 여 또는 C++ __asm 블록에서](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>