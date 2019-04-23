---
title: 컴파일러 오류 C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: 6f4157db4a2a1b1864446a082deddc73df2e2fe9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778711"
---
# <a name="compiler-error-c3062"></a>컴파일러 오류 C3062

'enum': 기본 형식 'type' 이므로 열거자 값이 필요

열거형에 대 한 기본 형식을 지정할 수 있습니다. 그러나 일부 형식에 각 열거자에 값을 할당 해야 합니다.

열거형에 대 한 자세한 내용은 참조 하세요. [enum 클래스](../../extensions/enum-class-cpp-component-extensions.md)합니다.

다음 샘플에서는 C3062 오류가 생성 됩니다.

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```