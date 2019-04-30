---
title: 컴파일러 경고(수준 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 293cbbcfe134f6cb4f5e1bf924be7c03fa278833
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408539"
---
# <a name="compiler-warning-level-1-c4325"></a>컴파일러 경고(수준 1) C4325

> 표준 섹션에 대 한 특성 '*섹션*' 무시

## <a name="remarks"></a>설명

표준 섹션의 특성을 변경할 수 없습니다. 예를 들어:

```cpp
#pragma section(".sdata", long)
```

이 덮어씁니다를 `.sdata` 를 사용 하는 표준 섹션의 **짧은** 데이터 형식을 **긴** 데이터 형식.

표준 섹션 변경할 수 없습니다 특성 포함

- .data

- .sdata

- .bss

- .sbss

- .text

- .const

- .sconst

- .rdata

- .srdata

추가 섹션은 나중에 추가할 수 있습니다.

## <a name="see-also"></a>참고자료

[section](../../preprocessor/section.md)