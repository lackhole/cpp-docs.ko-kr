---
title: 컴파일러 오류 C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: e9c385fd178dc967e72f5e0ca7fab27b28ad962f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400216"
---
# <a name="compiler-error-c3768"></a>컴파일러 오류 C3768

> 순수 관리 코드에서는 가상 vararg 함수의 주소를 가져올 수 없습니다.

## <a name="remarks"></a>설명

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

로 컴파일하는 경우 **/clr: pure**, 가상 주소를 가져올 수 없습니다. `vararg` 함수.

## <a name="example"></a>예제

다음 샘플에서는 C3768 오류가 생성 됩니다.

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```