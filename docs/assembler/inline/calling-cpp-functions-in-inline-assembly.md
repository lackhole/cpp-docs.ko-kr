---
title: 인라인 어셈블리에서 C++ 함수 호출
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: 666f7b2a59f0d48a14be54a439b6402f2a4d3128
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167272"
---
# <a name="calling-c-functions-in-inline-assembly"></a>인라인 어셈블리에서 C++ 함수 호출

**Microsoft 전용**

`__asm` 블록은 오버로드되지 않은 전역 C++ 함수만 호출할 수 있습니다. 오버로드된 전역 C++ 함수 또는 C++ 멤버 함수를 호출하면 컴파일러에서 오류가 발생합니다.

선언 된 함수를 호출할 수도 있습니다 **extern "C"** 링크 합니다. 이 통해는 `__asm` 내에서 블록을 C++ 할 라이브러리 함수를 선언 하는 모든 표준 헤더 파일 때문에 C 라이브러리 함수를 호출 하는 프로그램 **extern "C"** 링크 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[인라인 어셈블러](../../assembler/inline/inline-assembler.md)<br/>