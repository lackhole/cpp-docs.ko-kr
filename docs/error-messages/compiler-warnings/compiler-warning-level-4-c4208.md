---
title: 컴파일러 경고(수준 4) C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: 11c6b1ad50c44ac4ad2a9d014e57efef097d9d8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401179"
---
# <a name="compiler-warning-level-4-c4208"></a>컴파일러 경고(수준 4) C4208

비표준 확장이 사용 됨: delete [exp]-exp가 계산 되지만 무시

Microsoft 확장 (/Ze)을 사용 하 여는 괄호 안의 값을 사용 하 여 배열을 삭제할 수 있습니다 합니다 [delete 연산자](../../cpp/delete-operator-cpp.md)합니다. 값은 무시 됩니다.

```
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

이러한 값이 잘못 ANSI 호환성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).