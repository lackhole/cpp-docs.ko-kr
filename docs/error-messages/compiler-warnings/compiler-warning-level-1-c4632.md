---
title: 컴파일러 경고 (수준 1) C4632
ms.date: 11/04/2016
f1_keywords:
- C4632
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
ms.openlocfilehash: 4a24e54b443707775375a2adf833748eae347ce8
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052587"
---
# <a name="compiler-warning-level-1-c4632"></a>컴파일러 경고 (수준 1) C4632

XML 문서 주석: 파일 액세스 거부 됨: 원인

.Xdc 파일 (`file`)에 대 한 경로가 잘못 되었으며 .xdc 파일이 생성 되지 않았습니다.

다음 샘플에서는 C4632를 생성 합니다.

```cpp
// C4632.cpp
// compile with: /clr /docv:\\falsedir /LD /W1
// C4632 expected

/// Text for class MyClass.
public ref class MyClass {};
```