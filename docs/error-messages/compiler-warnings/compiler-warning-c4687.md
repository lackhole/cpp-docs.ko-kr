---
title: 컴파일러 경고 C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 83f5c535f9cf252783110838c181c88c8b0096ee
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631603"
---
# <a name="compiler-warning-c4687"></a>컴파일러 경고 C4687

> '*class*': 봉인 된 추상 클래스는 '*interface*' 인터페이스를 구현할 수 없습니다.

## <a name="remarks"></a>설명

봉인 된 추상 형식은 일반적으로 정적 멤버 함수를 보유 하는 데만 유용 합니다.

자세한 내용은 [abstract](../../extensions/abstract-cpp-component-extensions.md) 및 [sealed](../../extensions/sealed-cpp-component-extensions.md)를 참조 하세요.

C4687은 기본적으로 오류로 발급 됩니다. [Warning](../../preprocessor/warning.md) pragma를 사용 하 여 C4687를 억제할 수 있습니다. 봉인 된 추상 형식에서 인터페이스를 구현 하려는 경우 C4687를 표시 하지 않을 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4687를 생성 합니다.

```cpp
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```
