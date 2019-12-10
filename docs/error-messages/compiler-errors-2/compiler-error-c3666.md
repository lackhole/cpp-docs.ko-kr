---
title: 컴파일러 오류 C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: 990dea32b2928671f426235138698071fe038f63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758153"
---
# <a name="compiler-error-c3666"></a>컴파일러 오류 C3666

' constructor ': 재정의 지정자 ' keyword '는 생성자에서 사용할 수 없습니다.

재정의 지정 자가 생성자에서 사용 되었으며이는 허용 되지 않습니다. 자세한 내용은 [Override 지정자](../../extensions/override-specifiers-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3666를 생성 합니다.

```cpp
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```
