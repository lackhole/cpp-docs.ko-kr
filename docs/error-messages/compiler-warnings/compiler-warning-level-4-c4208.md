---
title: 컴파일러 경고(수준 4) C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: c6e83feacd08bdb2203873a14a47ebde686a94f9
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991614"
---
# <a name="compiler-warning-level-4-c4208"></a>컴파일러 경고(수준 4) C4208

비표준 확장이 사용 됨: delete [exp]-exp가 계산 되지만 무시 됩니다.

Microsoft 확장 (/Ze)을 사용 하면 [delete 연산자](../../cpp/delete-operator-cpp.md)를 사용 하 여 대괄호 내의 값을 사용 하 여 배열을 삭제할 수 있습니다. 값은 무시 됩니다.

```cpp
// C4208.cpp
// compile with: /W4
int main()
{
   int * MyArray = new int[18];
   delete [18] MyArray;      // C4208
   MyArray = new int[18];
   delete [] MyArray;        // ok
}
```

이러한 값은 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 유효 하지 않습니다.
