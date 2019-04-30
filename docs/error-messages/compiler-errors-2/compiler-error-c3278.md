---
title: 컴파일러 오류 C3278
ms.date: 11/04/2016
f1_keywords:
- C3278
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
ms.openlocfilehash: 7618336c08dd111e495d7e4102b8e61c6e927c39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382090"
---
# <a name="compiler-error-c3278"></a>컴파일러 오류 C3278

> 직접 호출 인터페이스 또는 순수 메서드 '*메서드*' 런타임 시 실패

## <a name="remarks"></a>설명

인터페이스 메서드 또는 순수 메서드를 호출했지만 허용되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3278을 생성합니다.

```cpp
// C3278_2.cpp
// compile with: /clr
using namespace System;
interface class I
{
   void vmf();
};

public ref class C: public I
{
public:
   void vmf()
   {
      Console::WriteLine( "In C::vmf()" );
      I::vmf(); // C3278
   }

};

int main()
{
   C^ pC = gcnew C;
   pC->vmf();
}
```