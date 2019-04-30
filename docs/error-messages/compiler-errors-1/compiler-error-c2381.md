---
title: 컴파일러 오류 C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: b29f7dac6c6d71e12eb0f003cdfc151dd2c349a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347901"
---
# <a name="compiler-error-c2381"></a>컴파일러 오류 C2381

'function': 재정의 __declspec (noreturn) 다른

함수를 선언 하 고 사용 되는 정의 하지만 다음 정의 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자입니다. 사용 `noreturn` 함수의 재정의; 선언 및 정의가 사용에 동의 해야 `noreturn`합니다.

다음 샘플에서는 C2381 오류가 생성 됩니다.

```
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```