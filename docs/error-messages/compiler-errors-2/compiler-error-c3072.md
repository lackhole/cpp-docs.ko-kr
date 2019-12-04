---
title: 컴파일러 오류 C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: a8fe0802a7529551fce1c0b7242c867db52d8842
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756762"
---
# <a name="compiler-error-c3072"></a>컴파일러 오류 C3072

' operator ' 연산자는 ref 클래스의 인스턴스에 적용할 수 없습니다.

단항 '`operator` ' 연산자를 사용 하 여 ref 클래스 인스턴스를 핸들 형식으로 변환

CLR 형식에는 native (또는 standard) 연산자가 아닌 CLR 연산자가 필요 합니다.  자세한 내용은 [추적 참조 연산자](../../extensions/tracking-reference-operator-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3072를 생성 합니다.

```cpp
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```
