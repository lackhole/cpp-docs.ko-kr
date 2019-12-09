---
title: 컴파일러 경고(수준 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: dc5127f8d7ef868903f8a26624f2d1dc54057a4c
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683256"
---
# <a name="compiler-warning-level-4-c4400"></a>컴파일러 경고(수준 4) C4400

' type ':이 형식에는 const/volatile 한정자를 사용할 수 없습니다.

[Const](../../cpp/const-cpp.md)및 [volatile](../../cpp/volatile-cpp.md)한정자는 공용 언어 런타임 형식의 변수와 함께 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4400를 생성 합니다.

```cpp
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```