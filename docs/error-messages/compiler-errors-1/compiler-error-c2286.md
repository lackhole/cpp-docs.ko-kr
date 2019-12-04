---
title: 컴파일러 오류 C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 79697a17d322ae15a21e522efa7dfd5c2342f7a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759167"
---
# <a name="compiler-error-c2286"></a>컴파일러 오류 C2286

' identifier ' 표현의 멤버에 대 한 포인터가 이미 ' 상속 '으로 설정 되었습니다. 선언이 무시 됩니다.

클래스에 대 한 두 개의 서로 다른 멤버 포인터 표현이 있습니다.

자세한 내용은 [상속 키워드](../../cpp/inheritance-keywords.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2286을 생성합니다.

```cpp
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
