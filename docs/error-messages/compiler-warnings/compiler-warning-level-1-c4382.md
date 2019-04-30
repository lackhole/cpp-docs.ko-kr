---
title: 컴파일러 경고(수준 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: cca2f8cc13cc8317bac3736e142ef58e126ed994
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390492"
---
# <a name="compiler-warning-level-1-c4382"></a>컴파일러 경고(수준 1) C4382

> throw '*형식*': __clrcall 소멸자 또는 복사 생성자를 사용 하 여 형식 /clr에서 낼 수 있습니다: 순수 모듈

## <a name="remarks"></a>설명

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

컴파일하면 **/clr** (되지 **/clr: pure**), 예외 처리를 네이티브 형식에 멤버 함수에 필요한 [__cdecl](../../cpp/cdecl.md) 아니라 [__clrcall](../../cpp/clrcall.md). 멤버 함수를 사용 하 여 네이티브 형식 `__clrcall` 호출 규칙으로 컴파일된 모듈에서 포착 없습니다 **/clr**합니다.

로 컴파일된 모듈에서 예외를 포착 됩니다 하는 경우 **/clr: pure**,이 경고를 무시할 수 있습니다.

자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플 C4382를 생성합니다.

```cpp
// C4382.cpp
// compile with: /clr /W1 /c
struct S {
   __clrcall ~S() {}
};

struct T {
   ~T() {}
};

int main() {
   S s;
   throw s;   // C4382

   S * ps = &s;
   throw ps;   // OK

   T t;
   throw t;   // OK
}
```