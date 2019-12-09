---
title: 컴파일러 경고(수준 4) C4365
ms.date: 11/04/2016
f1_keywords:
- C4365
helpviewer_keywords:
- C4365
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
ms.openlocfilehash: 554ead2d26a090eb1ffc86e532841143483b365a
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683032"
---
# <a name="compiler-warning-level-4-c4365"></a>컴파일러 경고(수준 4) C4365

' action ': ' type_1 '에서 ' type_2 ' (으)로 변환, signed/unsigned가 일치 하지 않습니다.

예를 들어 부호 없는 값을 부호 있는 값으로 변환 하려고 했습니다.

C4365은 기본적으로 해제 되어 있습니다.  자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4365를 생성 합니다.

```cpp
// C4365.cpp
// compile with: /W4
#pragma warning(default:4365)

int f(int) { return 0; }
void Test(size_t i) {}

int main() {
   unsigned int n = 10;
   int o = 10;
   n++;
   f(n);   // C4365
   f(o);   // OK

   Test( -19 );   // C4365
}
```