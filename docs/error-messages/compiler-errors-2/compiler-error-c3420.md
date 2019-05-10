---
title: 컴파일러 오류 C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3db109598ce0741ca34a230d8925994543bcb5ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182459"
---
# <a name="compiler-error-c3420"></a>컴파일러 오류 C3420

'finalizer': 종료자는 virtual일 수 없습니다.

종료자는 바깥쪽 형식에서 비가상으로만 호출할 수 있습니다. 따라서 가상 종료자를 선언하면 오류가 발생합니다.

자세한 내용은 참조 하세요. [소멸자 및 종료자 방법에서: 클래스 및 구조체 정의 및 사용 (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3420을 생성합니다.

```
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```