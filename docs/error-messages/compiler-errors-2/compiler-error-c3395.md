---
title: 컴파일러 오류 C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: 2e5234abcbe46e17035fd0b16e9816c879d86cfe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243052"
---
# <a name="compiler-error-c3395"></a>컴파일러 오류 C3395

'function': __declspec (dllexport)을 사용 하는 함수에 적용할 수 없습니다는 \__clrcall 호출 규칙

`__declspec(dllexport)` 및 [__clrcall](../../cpp/clrcall.md) 호환 되지 않습니다.  자세한 내용은 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)합니다.

다음 샘플에서는 C3395 오류가 생성 됩니다.

```
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```