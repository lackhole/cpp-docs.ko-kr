---
title: 컴파일러 오류 C2760
ms.date: 11/04/2016
f1_keywords:
- C2760
helpviewer_keywords:
- C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
ms.openlocfilehash: 5680de2fe0364d7cdc5e7ef017bd298423ea4c21
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273662"
---
# <a name="compiler-error-c2760"></a>컴파일러 오류 C2760

> 구문 오류 *: ' n*u l l '이 (가) '*name2*'가 아닙니다.

## <a name="remarks"></a>설명

여러 가지 방법으로이 오류를 발생 시킬 수 있습니다. 일반적으로는 컴파일러에서 의미가 없는 토큰 시퀀스로 인해 발생 합니다.

## <a name="example"></a>예제

이 샘플에서는 잘못 된 연산자와 함께 캐스팅 연산자를 사용 합니다.

```cpp
// C2760.cpp
class B {};
class D : public B {};

void f(B* pb) {
    D* pd1 = static_cast<D*>(pb);
    D* pd2 = static_cast<D*>=(pb);  // C2760
    D* pd3 = static_cast<D*=(pb);   // C2760
}
```
