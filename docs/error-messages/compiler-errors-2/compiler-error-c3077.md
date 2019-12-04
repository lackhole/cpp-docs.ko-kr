---
title: 컴파일러 오류 C3077
ms.date: 11/04/2016
f1_keywords:
- C3077
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
ms.openlocfilehash: b2dfe4c17ee122baa8f648669f9080b28584a66f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756736"
---
# <a name="compiler-error-c3077"></a>컴파일러 오류 C3077

'finalizer': 종료자는 참조 형식의 멤버만 될 수 있습니다.

종료자를 네이티브 또는 값 형식을 선언할 수 없습니다.

자세한 내용은 [방법: 클래스 및 구조체 정의 및 사용 (C++/Cli)의 소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3077을 생성합니다.

```cpp
// C3077.cpp
// compile with: /clr /c
value struct vs {
   !vs(){}   // C3077
};

ref struct rs {
protected:
   !rs(){}   // OK
};
```
