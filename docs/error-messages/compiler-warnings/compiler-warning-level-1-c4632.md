---
title: 컴파일러 경고(수준 1) C4632
ms.date: 11/04/2016
f1_keywords:
- C4632
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
ms.openlocfilehash: f1870da4f7889d79f5a4eabfcc3a95a21703e9fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393547"
---
# <a name="compiler-warning-level-1-c4632"></a>컴파일러 경고(수준 1) C4632

XML 문서 주석: 파일-액세스 거부: 이유

.Xdc 파일의 경로입니다 (`file`).xdc 파일이 생성 되지 및 올바르지 않습니다.

다음 샘플에서는 C4632 오류가 생성 됩니다.

```
// C4632.cpp
// compile with: /clr /docv:\\falsedir /LD /W1
// C4632 expected

/// Text for class MyClass.
public ref class MyClass {};
```