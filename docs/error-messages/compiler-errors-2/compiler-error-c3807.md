---
title: 컴파일러 오류 C3807
ms.date: 11/04/2016
f1_keywords:
- C3807
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
ms.openlocfilehash: a4b33782c0a1e5abb811210c9e7a28da7040c805
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755267"
---
# <a name="compiler-error-c3807"></a>컴파일러 오류 C3807

' type ': ComImport 특성이 있는 클래스는 ' type2 '에서 파생 될 수 없으며 인터페이스만 구현할 수 있습니다.

<xref:System.Runtime.InteropServices.ComImportAttribute>에서 파생 된 형식은 인터페이스만 구현할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3807를 생성 합니다.

```cpp
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```
