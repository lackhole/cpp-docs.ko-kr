---
title: 컴파일러 오류 C3624
ms.date: 11/04/2016
f1_keywords:
- C3624
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
ms.openlocfilehash: 3b4f71ed71ddb1b14ed51ccbcd420284ddcc70f6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761922"
---
# <a name="compiler-error-c3624"></a>컴파일러 오류 C3624

' type ':이 형식을 사용 하려면 ' assembly ' 어셈블리에 대 한 참조가 필요 합니다.

코드를 컴파일하는 데 필요한 어셈블리 (참조)가 지정 되지 않았습니다. 어셈블리를 [#using](../../preprocessor/hash-using-directive-cpp.md) 지시문에 전달 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3624를 생성 합니다.

```cpp
// C3624.cpp
// compile with: /clr /c
#using <System.Windows.Forms.dll>

// Uncomment the following 2 lines to resolve.
// #using <System.dll>
// #using <System.Drawing.dll>

using namespace System;

public ref class MyForm : public Windows::Forms::Form {};   // C3624
```
