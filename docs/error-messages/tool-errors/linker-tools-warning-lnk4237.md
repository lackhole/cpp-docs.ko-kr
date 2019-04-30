---
title: 링커 도구 경고 LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: 62ce0a0edc7f15bc5a19e4630133976f413da35a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352660"
---
# <a name="linker-tools-warning-lnk4237"></a>링커 도구 경고 LNK4237

'Dll';에서 가져올 때 지정한 /SUBSYSTEM:NATIVE /Subsystem: console 또는 /subsystem: windows를 사용 합니다.

[/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) Win32 windows 응용 프로그램을 빌드하는 직접 사용 하는 경우 다음 중 하나 이상 지정 되었습니다.

- kernel32.dll

- gdi32.dll

- user32.dll

- 하나는 msvcrt\* dll입니다.

지정 하지 않는 하 여이 경고를 해결할 **/SUBSYSTEM:NATIVE**합니다.