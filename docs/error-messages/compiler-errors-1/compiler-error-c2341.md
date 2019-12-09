---
title: 컴파일러 오류 C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 6147ce954c6d21d86f76d1fd8ec6b8a1a5070a12
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760051"
---
# <a name="compiler-error-c2341"></a>컴파일러 오류 C2341

' section name ': 세그먼트를 사용 하려면 먼저 #pragma data_seg, code_seg 또는 섹션을 사용 하 여 세그먼트를 정의 해야 합니다.

대입문은 [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md)또는 [section](../../preprocessor/section.md) pragma가 아직 정의 [하지 않은 세그먼트](../../cpp/allocate.md) 를 참조 합니다.

다음 샘플에서는 C2341를 생성 합니다.

```cpp
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

가능한 해결 방법:

```cpp
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```
