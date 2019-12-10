---
title: 컴파일러 오류 C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 95ca5ea846f9cd45bdb1e9706ae377589d37a285
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756021"
---
# <a name="compiler-error-c2665"></a>컴파일러 오류 C2665

' function ': number1 오버 로드는 ' type ' 형식에서 매개 변수 number2를 변환할 수 없습니다.

오버 로드 된 함수의 매개 변수를 필요한 형식으로 변환할 수 없습니다.  가능한 해결 방법은 다음과 같습니다.

- 변환 연산자를 제공 합니다.

- 명시적 변환을 사용 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2665를 생성 합니다.

```cpp
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```
