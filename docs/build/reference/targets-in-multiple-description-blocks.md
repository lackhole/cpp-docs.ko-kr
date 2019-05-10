---
title: 여러 개의 설명 블록에 포함된 대상
ms.date: 11/04/2016
helpviewer_keywords:
- description blocks
- blocks, multiple description
- multiple description blocks
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
ms.openlocfilehash: 03a6e1d0be44e12bb76767b7334ab647a6054b6e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317382"
---
# <a name="targets-in-multiple-description-blocks"></a>여러 개의 설명 블록에 포함된 대상

다른 명령을 사용 하 여 둘 이상의 설명 블록에 업데이트 하려면 대상 및 종속 항목 간의 연속 된 두 개의 콜론 (:)을 지정 합니다.

```
target.lib :: one.asm two.asm three.asm
    ml one.asm two.asm three.asm
    lib target one.obj two.obj three.obj
target.lib :: four.c five.c
    cl /c four.c five.c
    lib target four.obj five.obj
```

## <a name="see-also"></a>참고자료

[대상](targets.md)
