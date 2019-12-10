---
title: 컴파일러 오류 C2953
ms.date: 11/04/2016
f1_keywords:
- C2953
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
ms.openlocfilehash: 8a8d591bfbfa30a4ad2fbed171b5febbd46524b0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747672"
---
# <a name="compiler-error-c2953"></a>컴파일러 오류 C2953

'identifier': 클래스 템플릿이 이미 정의되었습니다.

소스 파일을 확인하고 다른 정의에 대한 파일을 포함합니다.

다음 샘플에서는 C2953을 생성합니다.

```cpp
// C2953.cpp
// compile with: /c
template <class T>  class A {};
template <class T>  class A {};   // C2953
template <class T>  class B {};   // OK
```
