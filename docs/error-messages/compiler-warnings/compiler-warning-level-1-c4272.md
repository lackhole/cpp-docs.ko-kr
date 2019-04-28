---
title: 컴파일러 경고(수준 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 26e136aa395729d520f4a71a06b6dc212cf21f8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208313"
---
# <a name="compiler-warning-level-1-c4272"></a>컴파일러 경고(수준 1) C4272

'function': __declspec (dllimport); 표시 함수를 가져올 때에 네이티브 호출 규칙을 지정 해야 합니다.

사용 하 여 표시 된 함수를 내보내려면 오류가 발생 합니다 [__clrcall](../../cpp/clrcall.md) 표시 된 함수를 가져오려는 경우이 경고가 발생 호출 규칙 및 컴파일러 `__clrcall`합니다.

다음 샘플에서는 C4272 오류가 생성 됩니다.

```
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```