---
title: 컴파일러 경고 (수준 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: f1db3eabc3b614019676dc4494e83104c62fe579
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627303"
---
# <a name="compiler-warning-level-1-c4218"></a>컴파일러 경고 (수준 1) C4218

비표준 확장이 사용 됨: 저장소 클래스 또는 형식을 하나 이상 지정 해야 합니다.

기본 Microsoft 확장 (/Ze)을 사용 하면 형식 또는 저장소 클래스를 지정 하지 않고 변수를 선언할 수 있습니다. 기본 형식은 `int`입니다.

## <a name="example"></a>예제

```cpp
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

이러한 선언은 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 유효 하지 않습니다.