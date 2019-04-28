---
title: 컴파일러 오류 C2448
ms.date: 11/04/2016
f1_keywords:
- C2448
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
ms.openlocfilehash: 915217ffbe848b2814e9960183854e09a80b9ee8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230298"
---
# <a name="compiler-error-c2448"></a>컴파일러 오류 C2448

'identifier': 함수 스타일 이니셜라이저가 함수 정의에 표시 됩니다.

함수 정의 올바르지 않습니다.

이 오류는 이전 스타일 C 언어 형식 목록에서 발생할 수 있습니다.

다음 샘플에서는 C2448 오류가 생성 됩니다.

```
// C2448.cpp
void func(c)
   int c;
{}   // C2448
```