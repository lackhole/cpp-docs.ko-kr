---
title: 컴파일러 경고(수준 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: cc80ddc459193c2e8fe5ca0b37d28d53d346fc53
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038111"
---
# <a name="compiler-warning-level-4-c4211"></a>컴파일러 경고(수준 4) C4211

비표준 확장이 사용 됨: extern에서 static로 재정의 되었습니다.

기본 Microsoft 확장 (/Ze)을 재정의할 수 있습니다는 `extern` 식별자 **정적**합니다.

## <a name="example"></a>예제

```
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

이러한 재정의 ANSI 규격 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="see-also"></a>참고자료

