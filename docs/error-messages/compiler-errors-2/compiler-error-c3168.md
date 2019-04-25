---
title: 컴파일러 오류 C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: f39160cc09825c6d87d56ff5ba80d21a35f41e12
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174162"
---
# <a name="compiler-error-c3168"></a>컴파일러 오류 C3168

'type': 열거형의 내부 형식이 잘못 되었습니다.

에 지정 된 형식의 기본는 `enum` 유형이 잘못 되었습니다. 기본 형식은 정수 계열 이어야 합니다 C++ 형식 또는 해당 CLR 형식입니다.

다음 샘플에서는 C3168를 생성합니다.

```
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
