---
title: 컴파일러 오류 C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 5e165a0c181bc27adebe75111050f49130305693
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756255"
---
# <a name="compiler-error-c3420"></a>컴파일러 오류 C3420

'finalizer': 종료자는 virtual일 수 없습니다.

종료자는 바깥쪽 형식에서 비가상으로만 호출할 수 있습니다. 따라서 가상 종료자를 선언하면 오류가 발생합니다.

자세한 내용은 [방법: 클래스 및 구조체 정의 및 사용 (C++/Cli)의 소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3420을 생성합니다.

```cpp
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```
