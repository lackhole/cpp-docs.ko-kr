---
title: 컴파일러 경고 C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: cac5918eb4a1689fd215e07272958eeca48247ad
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781902"
---
# <a name="compiler-warning-c4693"></a>컴파일러 경고 C4693

> 'class': 봉인 추상 클래스는 인스턴스 멤버 'Test'를 포함할 수 없습니다.

형식 표시 되 면 [봉인](../../extensions/sealed-cpp-component-extensions.md) 하 고 [추상](../../extensions/abstract-cpp-component-extensions.md), 정적 멤버를 하나만 사용할 수 있습니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4693을 생성합니다.

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```