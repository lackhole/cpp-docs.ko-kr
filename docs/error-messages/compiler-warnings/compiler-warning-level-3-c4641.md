---
title: 컴파일러 경고(수준 3) C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: 1e3eab6e96e829e3c3fd9304e757ba653e8f19b4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991812"
---
# <a name="compiler-warning-level-3-c4641"></a>컴파일러 경고(수준 3) C4641

XML 문서 주석에 모호한 상호 참조가 있습니다.

컴파일러가 참조를 명확 하 게 확인할 수 없습니다. 이 경고를 해결 하려면 참조를 명확 하 게 만드는 데 필요한 매개 변수 정보를 지정 합니다.

자세한 내용은 [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4641를 생성 합니다.

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
