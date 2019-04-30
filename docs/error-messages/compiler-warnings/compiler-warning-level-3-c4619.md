---
title: 컴파일러 경고(수준 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: 00647e7dafe18ffad2a059b960ebed0a0f4a5d36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401776"
---
# <a name="compiler-warning-level-3-c4619"></a>컴파일러 경고(수준 3) C4619

\#pragma 경고: 방법이 없는 경고 번호 '번호'

존재 하지 않는 경고를 사용 하지 않도록 설정 하려고 했습니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4619 오류가 생성 됩니다.

```
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```