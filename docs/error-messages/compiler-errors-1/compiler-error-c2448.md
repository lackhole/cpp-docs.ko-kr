---
title: 컴파일러 오류 C2448
ms.date: 11/04/2016
f1_keywords:
- C2448
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
ms.openlocfilehash: 8a71fe05e2a046a65b659840f94d104a3c526778
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744162"
---
# <a name="compiler-error-c2448"></a>컴파일러 오류 C2448

' identifier ': 함수 스타일 이니셜라이저가 함수 정의로 표시 됩니다.

함수 정의가 잘못 되었습니다.

이 오류는 이전 스타일의 C 언어 형식 목록으로 인해 발생할 수 있습니다.

다음 샘플에서는 C2448를 생성 합니다.

```cpp
// C2448.cpp
void func(c)
   int c;
{}   // C2448
```
