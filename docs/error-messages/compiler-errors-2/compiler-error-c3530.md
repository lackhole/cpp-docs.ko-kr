---
title: 컴파일러 오류 C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 3766eaa83457ba6cffaf8b1599983a065772911c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750145"
---
# <a name="compiler-error-c3530"></a>컴파일러 오류 C3530

' auto '는 다른 형식 지정자와 함께 사용할 수 없습니다.

형식 지정자는 `auto` 키워드와 함께 사용 됩니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. `auto` 키워드를 사용 하는 변수 선언에는 형식 지정자를 사용 하지 마십시오.

## <a name="example"></a>예제

다음 예에서는 변수 `x` `auto` 키워드와 형식 `int`으로 선언 되 고 예제가 **/zc: auto**를 사용 하 여 컴파일되기 때문에 C3530를 생성 합니다.

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>참조

[auto 키워드](../../cpp/auto-keyword.md)
