---
title: 컴파일러 오류 C3176
ms.date: 11/04/2016
f1_keywords:
- C3176
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
ms.openlocfilehash: c6e25d119846c7209ead5d3fe7e19b6273bf8583
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761701"
---
# <a name="compiler-error-c3176"></a>컴파일러 오류 C3176

' type ': 지역 값 형식을 선언할 수 없습니다.

전역 범위에서는 클래스를 값 형식 으로만 선언할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3176를 생성 합니다.

```cpp
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```
