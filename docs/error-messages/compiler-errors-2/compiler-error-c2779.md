---
title: 컴파일러 오류 C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: 9b4e0f255fd62801cb2010c109d05de89362bb9f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740002"
---
# <a name="compiler-error-c2779"></a>컴파일러 오류 C2779

' 선언 ': 속성 메서드는 비정적 데이터 멤버와만 연결 될 수 있습니다.

`property` 확장 특성이 정적 데이터 멤버에 잘못 적용 되었습니다.

다음 샘플에서는 C2779를 생성 합니다.

```cpp
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```
