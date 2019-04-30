---
title: 컴파일러 경고(수준 3) C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: 0a9ceb332888e306b8cb3bcbe1832f773d02d63d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401945"
---
# <a name="compiler-warning-level-3-c4414"></a>컴파일러 경고(수준 3) C4414

'function': 함수로 short 점프는 near로 변환

Short 점프 명령에서 제한 된 범위 내 주소 분기 되는 간단한 명령을 생성 합니다. 명령 이동 및 대상 주소를 함수 정의 간에 거리를 나타내는 short 오프셋을 포함 합니다. 링크 하는 동안 함수는 함수는 짧은 오프셋에서 도달할 수 있는 범위 밖으로 이동할 수 있는 이동 되거나 링크 타임 최적화를 수 있습니다. 컴파일러는 가까운 또는 훨씬 jmp 명령이 필요로 하는 점프에 대 한 특별 한 레코드를 생성 해야 합니다. 컴파일러가 변환 하도록 변경 합니다.

예를 들어, 다음 코드에서는 C4414를 생성합니다.

```
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```