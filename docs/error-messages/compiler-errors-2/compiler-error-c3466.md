---
title: 컴파일러 오류 C3466
ms.date: 11/04/2016
f1_keywords:
- C3466
helpviewer_keywords:
- C3466
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
ms.openlocfilehash: c51dffb1fd8c0a7ef962566635976acca8a3776f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742641"
---
# <a name="compiler-error-c3466"></a>컴파일러 오류 C3466

' type ': 제네릭 클래스의 특수화는 전달할 수 없습니다.

제네릭 클래스의 특수화에는 형식 전달을 사용할 수 없습니다.

자세한 내용은 [형식 전달 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 구성 요소를 만듭니다.

```cpp
// C3466.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

## <a name="example"></a>예제

다음 샘플에서는 C3466를 생성합니다.

```cpp
// C3466_b.cpp
// compile with: /clr /c
#using "C3466.dll"
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```
