---
title: 컴파일러 오류 C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: 6f60a9abbc5702c1a0d14d0f894c9b1684378c3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759362"
---
# <a name="compiler-error-c3238"></a>컴파일러 오류 C3238

'type': 이 이름의 형식이 이미 'assembly' 어셈블리에 전달되었습니다.

형식 전달 구문을 통해 참조된 어셈블리에서 정의된 형식이 클라이언트 애플리케이션에서도 정의되었습니다. 애플리케이션 범위에서 두 형식을 모두 정의할 수 없습니다.

자세한 내용은 [형식 전달C++(/cli)](../../extensions/type-forwarding-cpp-cli.md) 을 참조 하세요.

## <a name="example"></a>예제

다음 샘플은 다른 어셈블리에서 전달된 형식이 포함된 어셈블리를 만듭니다.

```cpp
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>예제

다음 샘플에서는 형식 정의를 포함하는 데 사용한 어셈블리를 만들지만 형식 전달 구문만 포함하지 않습니다.

```cpp
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>예제

다음 샘플에서는 C3238을 생성합니다.

```cpp
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```
