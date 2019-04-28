---
title: 링커 도구 경고 LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 0b18002135d225a90f7e45adc2ff57a64c0a79f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279322"
---
# <a name="linker-tools-warning-lnk4092"></a>링커 도구 경고 LNK4092

쓰기 가능한 공유 섹션 'section'에 재배치가 있습니다. 이미지가 올바르게 실행 되지 않을 수 있습니다.

링커는 잠재적으로 심각한 문제가 경고 메시지를 공유 섹션과 있을 때마다이 경고를 내보냅니다.

섹션을 "공유 합니다."로 표시 하는 여러 프로세스 간에 데이터를 공유 하는 한 가지 방법은 그러나 공유 섹션과 표시 문제가 발생할 수 있습니다. 예를 들어, 공유 데이터 섹션에서 다음과 같은 선언이 포함 된 DLL 해야 합니다.

```
int var = 1;
int *pvar = &var;
```

링커를 확인할 수 없습니다 `pvar` 메모리에서 DLL이 로드 되는 위치에 해당 값에 따라 달라, 따라서 배치 재배치 레코드 DLL입니다. 메모리의 주소에 DLL이 로드 하는 경우 `var` 해결할 수 있습니다 및 `pvar` 할당 합니다. 다른 프로세스가 동일한 DLL을 로드 동시에 로드할 수 없는 경우 주소, 주소에 재배치 `var` 첫 번째 프로세스의 주소 공간과 두 번째 프로세스에서 잘못 된 주소를 가리킵니다 업데이트 됩니다.