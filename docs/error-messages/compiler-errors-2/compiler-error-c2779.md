---
title: 컴파일러 오류 C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: 7cf8aed276ab2aea61dc92b9e9fcbff9552c2ad6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257051"
---
# <a name="compiler-error-c2779"></a>컴파일러 오류 C2779

'declaration': 속성 메서드는 비정적 데이터 멤버를 사용 하 여 연결할 수만

`property` 확장된 특성을 정적 데이터 멤버에 올바르게 적용 됩니다.

다음 샘플에서는 C2779를 생성합니다.

```
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```