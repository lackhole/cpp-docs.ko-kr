---
title: 컴파일러 오류 C2979
ms.date: 11/04/2016
f1_keywords:
- C2979
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
ms.openlocfilehash: e9b0af0d17ef57f19e051165b16632e3180159cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395315"
---
# <a name="compiler-error-c2979"></a>컴파일러 오류 C2979

제네릭에서는 명시적 특수화가 지원되지 않습니다.

제네릭 클래스가 잘못 선언되었습니다.  참조 [제네릭](../../extensions/generics-cpp-component-extensions.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2979를 생성합니다.

```
// C2979.cpp
// compile with: /clr /c
generic <>
ref class Utils {};   // C2979 error

generic <class T>
ref class Utils2 {};   // OK
```