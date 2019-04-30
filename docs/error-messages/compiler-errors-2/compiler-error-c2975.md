---
title: 컴파일러 오류 C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 66b7c0d61cbc8141b9ed3e5f6eb329b68eb00477
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344698"
---
# <a name="compiler-error-c2975"></a>컴파일러 오류 C2975

> '*인수*': 템플릿 인수가 잘못 되었습니다 '*형식*', 컴파일 타임 상수 식이 필요 합니다.

템플릿 인수는 템플릿 선언을; 맞지 않습니다. 상수 식 꺾쇠 괄호 안에 표시 됩니다. 변수는 템플릿 실제 인수로 허용 되지 않습니다. 템플릿 정의를 확인하여 올바른 형식을 찾습니다.

## <a name="example"></a>예제

다음 샘플 C2975 생성 하 고 또한 올바른 사용법을 보여 줍니다.

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

사용 하는 경우에 C2975 발생 &#95; &#95;줄&#95; &#95; 사용 하 여 컴파일 시간 상수로 [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)합니다. 한 가지 해결책으로 컴파일할 수 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) of **/ZI**합니다.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```