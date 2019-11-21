---
title: 컴파일러 경고 (수준 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: c293522e5d60d0edb4cc2da289e0ece71f89329f
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052210"
---
# <a name="compiler-warning-level-2-c4094"></a>컴파일러 경고 (수준 2) C4094

태그가 없는 ' token '은 기호를 선언 하지 않았습니다.

컴파일러가 태그가 없는 구조체, 공용 구조체 또는 클래스를 사용 하 여 빈 선언을 검색 했습니다. 선언이 무시 됩니다.

## <a name="example"></a>예제

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

이 조건은 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 오류를 생성 합니다.