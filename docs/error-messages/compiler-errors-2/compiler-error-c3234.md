---
title: 컴파일러 오류 C3234
ms.date: 11/04/2016
f1_keywords:
- C3234
helpviewer_keywords:
- C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
ms.openlocfilehash: fd6e918c115ed121dda5d589a62b1a94d14184a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175267"
---
# <a name="compiler-error-c3234"></a>컴파일러 오류 C3234

제네릭 클래스는 제네릭 형식 매개 변수에서 상속할 수 없습니다.

제네릭 클래스는 제네릭 형식 매개 변수에서 상속할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3234를 생성합니다.

```
// C3234.cpp
// compile with: /clr /c
generic <class T>
public ref class C : T {};   // C3234
// try the following line instead
// public ref class C {};
```