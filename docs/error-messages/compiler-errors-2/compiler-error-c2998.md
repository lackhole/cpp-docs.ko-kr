---
title: 컴파일러 오류 C2998
ms.date: 11/04/2016
f1_keywords:
- C2998
helpviewer_keywords:
- C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
ms.openlocfilehash: 2a9b4190cab9589fbe7419cba7ec94e49bb6d9ba
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742407"
---
# <a name="compiler-error-c2998"></a>컴파일러 오류 C2998

'identifier': 템플릿 정의일 수 없습니다.

컴파일러에서 템플릿 정의에 사용되는 구문을 처리할 수 없습니다.

다음 샘플에서는 C2998을 생성합니다.

```cpp
// C2998.cpp
// compile with: /c
template <class T> int x = 1018; // C2998
```
