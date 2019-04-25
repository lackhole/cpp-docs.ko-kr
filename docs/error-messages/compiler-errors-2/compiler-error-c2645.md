---
title: 컴파일러 오류 C2645
ms.date: 11/04/2016
f1_keywords:
- C2645
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
ms.openlocfilehash: 9df9f41da3d4cbef97511b979845c5a6b404614b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152594"
---
# <a name="compiler-error-c2645"></a>컴파일러 오류 C2645

멤버에 대 한 포인터에 대 한 정규화 된 이름이 없는 (찾을 수 ':: *')

멤버에 대 한 포인터의 선언에서 클래스를 지정 하지 않습니다.

다음 샘플에서는 C2645 오류가 생성 됩니다.

```
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```