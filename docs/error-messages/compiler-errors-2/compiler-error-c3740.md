---
title: 컴파일러 오류 C3740
ms.date: 11/04/2016
f1_keywords:
- C3740
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
ms.openlocfilehash: dd493e4759b2fb70918bf94f14f4ada022e326b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227003"
---
# <a name="compiler-error-c3740"></a>컴파일러 오류 C3740

템플릿 원본 또는 이벤트를 수신할 수 없습니다.

템플릿 기반 클래스 또는 구조체를 포함할 수 없습니다 [이벤트](../../cpp/event-handling.md)합니다.

다음 샘플에서는 C3740 오류가 생성 됩니다.

```
// C3740.cpp
template <typename T>   // Delete the template specification
struct E {
   __event void f();   // C3740
};

int main() {
}
```