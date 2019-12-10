---
title: 컴파일러 오류 C3914
ms.date: 11/04/2016
f1_keywords:
- C3914
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
ms.openlocfilehash: 6f7da67871b5e6b9d7da9a9aa4eebeb761f8cc50
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738000"
---
# <a name="compiler-error-c3914"></a>컴파일러 오류 C3914

기본 속성은 정적일 수 없습니다.

기본 속성이 잘못 선언 되었습니다.  자세한 내용은 [방법:/cli에서 C++속성 사용](../../dotnet/how-to-use-properties-in-cpp-cli.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3914를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C3914.cpp
// compile with: /clr /c
ref struct X {
   static property int default[int] {   // C3914
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```
