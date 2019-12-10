---
title: 컴파일러 오류 C3740
ms.date: 11/04/2016
f1_keywords:
- C3740
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
ms.openlocfilehash: 4e32c37853f4c877e6260e38daa0c8357ca54a25
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752667"
---
# <a name="compiler-error-c3740"></a>컴파일러 오류 C3740

템플릿은 이벤트를 보내거나 받을 수 없습니다.

템플릿 기반 클래스 또는 구조체는 [이벤트](../../cpp/event-handling.md)를 포함할 수 없습니다.

다음 샘플에서는 C3740를 생성 합니다.

```cpp
// C3740.cpp
template <typename T>   // Delete the template specification
struct E {
   __event void f();   // C3740
};

int main() {
}
```
