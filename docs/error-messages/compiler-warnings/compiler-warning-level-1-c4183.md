---
title: 컴파일러 경고 (수준 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 0d947a0f6d777a5ed3191d6d232a604028be2003
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391623"
---
# <a name="compiler-warning-level-1-c4183"></a>컴파일러 경고 (수준 1) C4183

'identifier': 반환 형식이; 없습니다 'int'를 반환 하는 멤버 함수로 간주

인라인 정의 클래스 또는 구조체에서 멤버 함수의 반환 형식이 없습니다. 이 멤버 함수는 기본 유형의 반환으로 간주 됩니다 `int`합니다.

다음 샘플에서는 C4183 오류가 생성 됩니다.

```
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```