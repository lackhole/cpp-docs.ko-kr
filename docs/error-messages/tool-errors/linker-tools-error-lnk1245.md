---
title: 링커 도구 오류 LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 4cf9a6c4356872b727a10a360396e51e38928b29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160564"
---
# <a name="linker-tools-error-lnk1245"></a>링커 도구 오류 LNK1245

잘못 된 하위 시스템 '하위 시스템'; / 하위 시스템은 WINDOWS, WINDOWSCE 또는 CONSOLE 이어야 합니다.

[/clr](../../build/reference/clr-common-language-runtime-compilation.md) 개체를 컴파일하는 데 사용 된 다음 조건 중 하나가 했는데:

- 사용자 지정 진입점이 정의 되었습니다 ([/ENTRY](../../build/reference/entry-entry-point-symbol.md))는 같은 링커 하위 시스템을 유추할 수 없습니다.

- 에 전달 된 값을 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) /clr 개체에 대 한 잘못 된 링커 옵션입니다.

두 경우 모두에 대 한 해결 방법을 /SUBSYSTEM 링커 옵션에 유효한 값을 지정 하는 것입니다.