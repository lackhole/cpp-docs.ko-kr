---
title: 컴파일러 경고(수준 3) C4622
ms.date: 11/04/2016
f1_keywords:
- C4622
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
ms.openlocfilehash: 88a41c7f9edb1d2a9f6d4547336a77bd5e362882
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401750"
---
# <a name="compiler-warning-level-3-c4622"></a>컴파일러 경고(수준 3) C4622

미리 컴파일된 헤더를 'file' 개체 파일에 만드는 동안 생성된 디버그 정보를 덮어쓰고 있습니다.

[/Yu](../../build/reference/yu-use-precompiled-header-file.md) (미리 컴파일된 헤더 사용) 옵션으로 컴파일할 때 지정된 파일의 CodeView 정보가 손실되었습니다.

미리 컴파일된 헤더 파일을 만들거나 사용할 때 [/Fo](../../build/reference/fo-object-file-name.md)를 사용하여 개체 파일의 이름을 바꾸고 새 개체 파일을 사용하여 연결합니다.