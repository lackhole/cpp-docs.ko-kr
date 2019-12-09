---
title: 컴파일러 오류 C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 3e495a8019405a558511637467133877dae1183e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743525"
---
# <a name="compiler-error-c2480"></a>컴파일러 오류 C2480

' identifier ': ' thread '는 정적 범위의 데이터 항목에만 사용할 수 있습니다.

자동 변수, 비정적 데이터 멤버, 함수 매개 변수 또는 함수 선언 또는 정의에는 `thread` 특성을 사용할 수 없습니다.

전역 변수, 정적 데이터 멤버 및 지역 정적 변수에만 `thread` 특성을 사용 합니다.

다음 샘플에서는 C2480를 생성 합니다.

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
