---
title: 컴파일러 경고(수준 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: 982e7da5523f76a3ff205778318a75076a8c04d1
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189176"
---
# <a name="compiler-warning-level-3-c4619"></a>컴파일러 경고(수준 3) C4619

\#pragma warning: 경고 번호 ' number '가 없습니다.

존재 하지 않는 경고를 사용 하지 않도록 설정 하려고 한 경우

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4619를 생성 합니다.

```cpp
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```