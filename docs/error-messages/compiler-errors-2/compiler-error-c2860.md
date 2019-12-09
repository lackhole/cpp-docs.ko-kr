---
title: 컴파일러 오류 C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 6a6bb4bc12e791e36a31ffc4cf417e21cb71dbdd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760969"
---
# <a name="compiler-error-c2860"></a>컴파일러 오류 C2860

' void '는 ' (void) '를 제외한 인수 형식일 수 없습니다.

다른 인수를 사용 하 여 형식 `void`를 인수 형식으로 사용할 수 없습니다.

다음 샘플에서는 C2860를 생성 합니다.

```cpp
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```
