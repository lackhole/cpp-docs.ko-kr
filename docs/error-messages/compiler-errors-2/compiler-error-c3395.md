---
title: 컴파일러 오류 C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: eaf63b42a6c44153a55d8aeb70f4f1174a5c895c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737545"
---
# <a name="compiler-error-c3395"></a>컴파일러 오류 C3395

' function ': __declspec (dllexport)은 (는) \__clrcall 호출 규칙을 사용 하 여 함수에 적용할 수 없습니다.

`__declspec(dllexport)`와 [__clrcall](../../cpp/clrcall.md) 호환 되지 않습니다.  자세한 내용은 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)를 참조하세요.

다음 샘플에서는 C3395를 생성 합니다.

```cpp
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```
