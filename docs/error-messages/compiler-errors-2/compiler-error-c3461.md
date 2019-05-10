---
title: 컴파일러 오류 C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: a674ce7819c88dd4e26355c0129a6c181da5c276
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222308"
---
# <a name="compiler-error-c3461"></a>컴파일러 오류 C3461

'type': 관리되는 형식만 전달할 수 있습니다.

형식 전달은 CLR 형식에서만 발생할 수 있습니다.  참조 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md) 자세한 내용은 합니다.

자세한 내용은 [형식 전달 (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 구성 요소를 만듭니다.

```
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>예제

다음 샘플에서는 C3461을 생성합니다.

```
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```