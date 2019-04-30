---
title: 컴파일러 오류 C3748
ms.date: 11/04/2016
f1_keywords:
- C3748
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
ms.openlocfilehash: ef1c446f9feb3d40add62513a31fc81a382b98e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226845"
---
# <a name="compiler-error-c3748"></a>컴파일러 오류 C3748

'interface': 관리 되는 인터페이스 이벤트를 발생 하지 않을 수 있습니다

합니다 [__event](../../cpp/event.md) 키워드는 인터페이스 내에서 사용할 수 없습니다.

다음 샘플에서는 C3748 오류가 생성 됩니다.

```
// C3748.cpp
__interface I {
// try the following line instead
// struct I {
   __event void f();   // C3748
};

int main() {
}
```