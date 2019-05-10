---
title: 컴파일러 오류 C2777
ms.date: 11/04/2016
f1_keywords:
- C2777
helpviewer_keywords:
- C2777
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
ms.openlocfilehash: cfbe2c729141108565f00b7b5a7fd581b49e516d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227704"
---
# <a name="compiler-error-c2777"></a>컴파일러 오류 C2777

속성 당 'put' 메서드 하나만 지정할 수 있습니다.

A [속성](../../cpp/property-cpp.md) declspec 한정자가 둘 이상의 `put` 속성입니다.

다음 샘플에서는 C2777 오류가 생성 됩니다.

```
// C2777.cpp
struct A {
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777
   // try the following line instead
   // __declspec(property(put=PutProp))
      int prop;
   int PutProp(void);
   int PutPropToo(void);
};
```