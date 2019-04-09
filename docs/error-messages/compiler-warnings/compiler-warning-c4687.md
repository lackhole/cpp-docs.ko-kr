---
title: 컴파일러 경고 C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 1978e1a35ba5b5d59b5961a21378d8af6921d145
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778665"
---
# <a name="compiler-warning-c4687"></a>컴파일러 경고 C4687

'class': 봉인된 추상 클래스는 'interface' 인터페이스를 구현할 수 없습니다

봉인 된 추상 형식은 일반적으로 정적 멤버 함수를 유지 하는 데만 합니다.

자세한 내용은 [추상](../../extensions/abstract-cpp-component-extensions.md)하 고 [봉인](../../extensions/sealed-cpp-component-extensions.md)합니다.

기본적으로 C4687 오류로 발생 합니다. C4687 표시 하지 않을 수 있습니다 합니다 [경고](../../preprocessor/warning.md) pragma입니다. 인 경우 추상, 봉인 된 형식에서 인터페이스를 구현 하려는 특정 C4687 억제할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C4687를 생성합니다.

```
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```