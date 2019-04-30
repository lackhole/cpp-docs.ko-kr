---
title: 컴파일러 오류 C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: 2df788efd93fb531822d858ea5aee1722487db81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387045"
---
# <a name="compiler-error-c2261"></a>컴파일러 오류 C2261

'string': 어셈블리 참조가 잘못 되어 확인할 수 없습니다

값이 잘못 되었습니다.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> friend 어셈블리를 지정 하는 데 사용 됩니다. 예를 들어 a.dll b.dll를 friend 어셈블리로 지정 하려고 합니다 (a.dll)에서 지정 하면 됩니다. InternalsVisibleTo("b"). 런타임에서 b.dll a.dll (제외 개인 형식)에서 모든 항목에 액세스할 수 있게 합니다.

Friend 어셈블리를 지정 하는 경우에 올바른 구문에 자세한 내용은 참조 하십시오 [Friend 어셈블리 (C++)](../../dotnet/friend-assemblies-cpp.md)합니다.

## <a name="example"></a>예제

다음 샘플 C2261를 생성합니다.

```
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```