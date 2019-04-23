---
title: 컴파일러 오류 C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: 1a3d0d754557bbc811d1017ed1491181333e82dc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776472"
---
# <a name="compiler-error-c3869"></a>컴파일러 오류 C3869

gcnew 제약 조건에 빈 매개 변수 목록 '(가 없습니다.

`gcnew` 빈 매개 변수 목록을 사용 하지 않고 특수 제약 조건을 지정 했습니다. 참조 [제네릭 형식 매개 변수에 대 한 제약 조건 (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 에 대 한 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C3869를 생성합니다.

```
// C3869.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : gcnew   // C3869
// try the following line instead
// where T : gcnew()
ref class List {};
```