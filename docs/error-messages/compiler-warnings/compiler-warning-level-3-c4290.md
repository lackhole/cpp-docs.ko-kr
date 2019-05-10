---
title: 컴파일러 경고(수준 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: c585294686298a1197d437d41a0d541f1268985f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402088"
---
# <a name="compiler-warning-level-3-c4290"></a>컴파일러 경고(수준 3) C4290

C++예외 사양은 나타내는 함수를 제외 하 고 무시 됩니다. __declspec (nothrow) 아닙니다.

예외 사양에는 시각적 개체를 사용 하 여 함수를 선언 하는 C++ 를 허용 하지만 구현 하지 않습니다. 다시 컴파일되지 않아도 컴파일 중에 무시 되는 지정 해야 하는 예외를 사용 하 여 코드와 연결 되도록 다시 나중에 예외 사양을 지 원하는 버전.

자세한 내용은 [예외 사양 (throw)](../../cpp/exception-specifications-throw-cpp.md) 합니다.

사용 하 여이 경고를 방지할 수 있습니다 합니다 [경고](../../preprocessor/warning.md) pragma:

```
#pragma warning( disable : 4290 )
```

다음 코드 샘플에서는 C4290 오류가 생성 됩니다.

```
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```