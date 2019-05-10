---
title: 컴파일러 오류 C2930
ms.date: 11/04/2016
f1_keywords:
- C2930
helpviewer_keywords:
- C2930
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
ms.openlocfilehash: 20fa3e81e66bb30bd63e579a863b6071de4ef871
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385760"
---
# <a name="compiler-error-c2930"></a>컴파일러 오류 C2930

'class': type-class-id가 'enum identifier' 열거자로 재정의되었습니다.

제네릭 또는 템플릿 클래스를 열거형의 멤버로 사용할 수 없습니다.

중괄호가 짝이 맞지 않는 경우 이 오류가 발생할 수 있습니다.

다음 샘플에서는 C2930을 생성합니다.

```
// C2930.cpp
// compile with: /c
template<class T>
class x{};
enum SomeEnum { x };   // C2930

class y{};
enum SomeEnum { y };
```

C2930은 제네릭을 사용하는 경우에도 발생할 수 있습니다.

```
// C2930c.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
enum SomeEnum { GC };   // C2930

ref struct GC2 {};
enum SomeEnum2 { GC2 };
```