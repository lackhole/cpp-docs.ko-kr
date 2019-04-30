---
title: 컴파일러 경고(수준 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 36d5de3b1270b41edfc391df960a556aca207709
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386475"
---
# <a name="compiler-warning-level-1-c4218"></a>컴파일러 경고(수준 1) C4218

비표준 확장이 사용 됨: 저장소 클래스 또는 형식을 지정 해야 합니다

기본 Microsoft 확장 (/Ze)을 사용 하 여 형식 또는 저장소 클래스를 지정 하지 않고 변수를 선언할 수 있습니다. 기본 형식은 `int`입니다.

## <a name="example"></a>예제

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

이러한 선언이 ANSI 호환성 올바르지 않습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).