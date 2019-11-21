---
title: Compiler Warning (level 3) C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: 0a930490f7b53fbbb31abb0f621cf972295d2ea6
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189419"
---
# <a name="compiler-warning-level-3-c4641"></a>Compiler Warning (level 3) C4641

XML 문서 주석에 모호한 상호 참조가 있습니다.

The compiler was unable to unambiguously resolve a reference. To resolve this warning, specify the parameter information necessary to make the reference unambiguous.

자세한 내용은 [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md)을 참조하세요.

## <a name="example"></a>예제

The following sample generates C4641.

```cpp
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```