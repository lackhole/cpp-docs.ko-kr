---
title: 컴파일러 오류 C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 4e26742de6c294018f81c6f49c1719fdb11d5149
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328538"
---
# <a name="compiler-error-c3704"></a>컴파일러 오류 C3704

'function': vararg 메서드 이벤트를 발생 시킬 수 없습니다.

사용 하려는 [__event](../../cpp/event.md) vararg 메서드. 이 오류를 해결 하려면 대체는 `fireEvent(int i, ...)` 호출을 `fireEvent(int i)` 다음 코드 예제와 같이 호출 합니다.

다음 샘플에서는 C3704 오류가 생성 됩니다.

```
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```