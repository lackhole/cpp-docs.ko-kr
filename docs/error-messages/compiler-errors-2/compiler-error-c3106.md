---
title: 컴파일러 오류 C3106
ms.date: 11/04/2016
f1_keywords:
- C3106
helpviewer_keywords:
- C3106
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
ms.openlocfilehash: 85aef1937ccbdbbbc335e4166fab11aa982b1839
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755839"
---
# <a name="compiler-error-c3106"></a>컴파일러 오류 C3106

' attribute ': 명명 되지 않은 인수는 명명 된 인수 앞에와 야 합니다.

명명 되지 않은 인수는 명명 된 인수 앞에 있는 특성에 전달 해야 합니다.

자세한 내용은 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3106를 생성 합니다.

```cpp
// C3106.cpp
// compile with: /c
[module(name="MyLib", dll)];   // C3106
[module(dll, name="MyLib")];   // OK
```
