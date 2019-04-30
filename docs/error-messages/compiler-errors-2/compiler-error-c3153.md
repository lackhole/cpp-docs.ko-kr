---
title: 컴파일러 오류 C3153
ms.date: 11/04/2016
f1_keywords:
- C3153
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
ms.openlocfilehash: 62b9e7499c52153183f14eae47c488da6a59b458
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374874"
---
# <a name="compiler-error-c3153"></a>컴파일러 오류 C3153

'interface': 인터페이스의 인스턴스를 만들 수 없습니다.

인터페이스를 인스턴스화할 수 없습니다. 인터페이스의 멤버를 사용 하려면 인터페이스에서 클래스를 파생 인터페이스 멤버를 구현 하 고 멤버를 사용 하 여 합니다.

다음 샘플에서는 C3153 오류가 생성 됩니다.

```
// C3153.cpp
// compile with: /clr
interface class A {
};

int main() {
   A^ a = gcnew A;   // C3153
}
```
