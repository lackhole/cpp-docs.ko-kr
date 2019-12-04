---
title: 컴파일러 오류 C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: ae8931d3b139e0e7e7aa947ffea16700e2f12302
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736713"
---
# <a name="compiler-error-c3869"></a>컴파일러 오류 C3869

gcnew 제약 조건에 빈 매개 변수 목록 ' () '가 없습니다.

빈 매개 변수 목록을 사용 하지 않고 `gcnew` 특수 제약 조건을 지정 했습니다. 자세한 내용은 [제네릭 형식 매개 변수에 대C++한 제약 조건 (/cli)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3869를 생성 합니다.

```cpp
// C3869.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : gcnew   // C3869
// try the following line instead
// where T : gcnew()
ref class List {};
```
