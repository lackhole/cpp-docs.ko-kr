---
title: 컴파일러 경고(수준 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: 6a7d760a7d192c7e0a7bd5e16f77efe1a4099c31
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391493"
---
# <a name="compiler-warning-level-4-c4434"></a>컴파일러 경고(수준 4) C4434

클래스 생성자의 액세스 가능성은 private 있어야 합니다. 개인 액세스로 변경합니다.

C4434는 컴파일러는 정적 생성자의 액세스 가능성 변경 되었음을 나타냅니다. 정적 생성자는 공용 언어 런타임에 의해 호출 될 으로만 private 액세스 가능성이 있어야 합니다. 자세한 내용은 [정적 생성자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors)합니다.

## <a name="example"></a>예제

다음 샘플 C4434를 생성합니다.

```
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```