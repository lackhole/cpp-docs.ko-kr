---
title: 컴파일러 오류 C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: edca117da585fee731041d696e05af1baf6d3e5c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778678"
---
# <a name="compiler-error-c3666"></a>컴파일러 오류 C3666

'constructor': 재정의 지정자는 'keyword' 생성자를 사용할 수 없습니다

생성자에는 재정의 지정자를 사용한 및 허용 되지 않습니다. 자세한 내용은 [재정의 지정자](../../extensions/override-specifiers-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3666를 생성합니다.

```
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```