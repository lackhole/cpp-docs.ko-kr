---
title: 컴파일러 경고(수준 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: fccc37ec531768adbe332ddf9fd91ceb708c7185
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990819"
---
# <a name="compiler-warning-level-4-c4434"></a>컴파일러 경고(수준 4) C4434

클래스 생성자에는 private 액세스 가능성이 있어야 합니다. 개인 액세스로 변경

C4434은 컴파일러가 정적 생성자의 액세스 가능성을 변경 했음을 나타냅니다. 정적 생성자는 공용 언어 런타임에 의해서만 호출 되기 때문에 private 액세스 가능성이 있어야 합니다. 자세한 내용은 [정적 생성자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4434를 생성 합니다.

```cpp
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```
