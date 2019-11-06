---
title: 컴파일러 경고 C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: 661b687373d6c72b9f40a05d1406bc89ce332133
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623711"
---
# <a name="compiler-warning-c4430"></a>컴파일러 경고 C4430

형식 지정자가 없습니다. int로 가정합니다. 참고: C++ 는 기본값-int를 지원 하지 않습니다.

이 오류는 Visual Studio 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다. 모든 선언에서 명시적으로 형식을 지정 해야 합니다. int는 더 이상 가정 되지 않습니다.

C4430는 항상 오류로 실행 됩니다.  `#pragma warning` 또는 **/wd**를 사용 하 여이 경고를 해제할 수 있습니다. 자세한 내용은 [warning](../../preprocessor/warning.md) 또는 [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/wd,/we,/wo,/Wv,/Wx (경고 수준)](../../build/reference/compiler-option-warning-level.md) 를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4430를 생성 합니다.

```cpp
// C4430.cpp
// compile with: /c
struct CMyClass {
   CUndeclared m_myClass;  // C4430
   int m_myClass;  // OK
};

typedef struct {
   POINT();   // C4430
   // try the following line instead
   // int POINT();
   unsigned x;
   unsigned y;
} POINT;
```