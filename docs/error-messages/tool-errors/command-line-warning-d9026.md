---
title: 명령줄 경고 D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 3fd8d442dfabaf2f03d8b564c9fdfb1537f6ff28
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214209"
---
# <a name="command-line-warning-d9026"></a>명령줄 경고 D9026

옵션이 전체 명령줄에 적용

파일 이름 지정 된 명령에는 옵션이 지정 되었습니다. 옵션은 파일 앞에 오는 것에 적용 되었습니다.

예를 들어, 명령에서

```
CL verdi.c /G5 puccini.c
```

사용/g5, / g4 기본값이 아닌 VERDI.c 파일은 컴파일됩니다.

이 동작은 VERDI.c 생성 파일 이름 앞에 지정 된 옵션을 사용 하 여 컴파일할 / G4 및 PUCCINI.c/g5를 사용 하 여 컴파일 중인를 적용 하는 일부 이전 버전의 다릅니다.