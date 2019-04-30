---
title: 링커 도구 경고 LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: dc81df89609f59834c8a3271dd64f3b99b281f90
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395081"
---
# <a name="linker-tools-warning-lnk4206"></a>링커 도구 경고 LNK4206

> 미리 컴파일된 형식 정보를 찾을 수 없습니다. '*filename*' 링크 되지 않았거나 덮어 쓰여졌습니다. 디버그 정보가 없는 것 처럼 개체를 링크 합니다.

합니다 *filename* 사용 하 여 컴파일된 개체 파일 [/Yc](../../build/reference/yc-create-precompiled-header-file.md), LINK 명령에 지정 되지 않았거나 덮어 쓰여졌습니다.

이 경고에 대 한 일반적인 시나리오 중 이며 /Yc를 사용 하 여 컴파일된.obj 라이브러리에 있는 경우 코드에서.obj 기호 참조가 없는 경우  이런 경우 링커는 하지 사용 하 여 (또는 그 역시 볼).obj 파일  이 경우 코드를 다시 컴파일하거나 하 고 사용 해야 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 사용 하 여 컴파일된 개체에 대 한 [/Yu](../../build/reference/yu-use-precompiled-header-file.md)합니다.