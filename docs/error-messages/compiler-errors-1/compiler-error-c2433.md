---
title: 컴파일러 오류 C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: 9edb30e574e212bd30fd60dd3ce5aaddc650dc11
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744435"
---
# <a name="compiler-error-c2433"></a>컴파일러 오류 C2433

' identifier ': ' modifier '는 데이터 선언에 사용할 수 없습니다.

`friend`, `virtual`및 `inline` 한정자는 데이터 선언에 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2433를 생성 합니다.

```cpp
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```
