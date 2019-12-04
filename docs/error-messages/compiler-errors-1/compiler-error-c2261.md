---
title: 컴파일러 오류 C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: f23c2a38f8e4d6781af73fb70a25cf4737e2c4e8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758777"
---
# <a name="compiler-error-c2261"></a>컴파일러 오류 C2261

' string ': 어셈블리 참조가 잘못 되어 확인할 수 없습니다.

값이 잘못 되었습니다.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>은 friend 어셈블리를 지정 하는 데 사용 됩니다. 예를 들어 .dll에서 b .dll을 friend 어셈블리로 지정 하려는 경우 (.dll에서): InternalsVisibleTo ("b")를 지정 합니다. 그러면 런타임에서는 전용 형식을 제외 하 고 .dll의 모든 항목에 액세스할 수 있습니다.

Friend 어셈블리를 지정할 때 올바른 구문에 대 한 자세한 내용은 [Friend 어셈블리 (C++)](../../dotnet/friend-assemblies-cpp.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2261를 생성 합니다.

```cpp
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```
