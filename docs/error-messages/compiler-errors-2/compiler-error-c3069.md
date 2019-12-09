---
title: 컴파일러 오류 C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: 230d2569ea314bde2ea9ef0c4fc58d1a9743807f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749518"
---
# <a name="compiler-error-c3069"></a>컴파일러 오류 C3069

'operator': 열거형 형식에 사용할 수 없습니다.

CLR 열거형에 대해서는 연산자가 지원되지 않습니다.  자세한 내용은 [방법:/cli에서 C++열거형 정의 및 사용](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3069를 생성합니다.

```cpp
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```
