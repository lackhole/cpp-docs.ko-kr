---
title: 컴파일러 오류 C3118
ms.date: 11/04/2016
f1_keywords:
- C3118
helpviewer_keywords:
- C3118
ms.assetid: 40fbe681-8868-4cb2-a2b2-4db4449319a7
ms.openlocfilehash: 072bb821a9dc2547c9a2758fb1ca542bdbc66f86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281692"
---
# <a name="compiler-error-c3118"></a>컴파일러 오류 C3118

'interface': 인터페이스가 가상 상속을 지원 하지 않습니다

거의 인터페이스에서 상속 하려고 했습니다. 예를 들면 다음과 같습니다.

```
// C3118.cpp
__interface I1 {
};

__interface I2 : virtual I1 {   // C3118
};
```

이 오류를 생성합니다.