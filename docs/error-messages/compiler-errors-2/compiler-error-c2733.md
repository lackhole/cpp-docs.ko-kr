---
title: 컴파일러 오류 C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 26819f1928223b5fa96d275290105f32787057f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208326"
---
# <a name="compiler-error-c2733"></a>컴파일러 오류 C2733

'function' 없습니다 오버 로드 된 함수의 두 번째 C 링크

둘 이상의 오버 로드 된 함수는 C 링크를 사용 하 여 선언 됩니다. C 링크를 사용 하 여, 지정된 된 함수 하나만 형식의 외부 될 수 있습니다. 오버 로드 된 함수 데코 레이트 되지 않은 이름이 없으므로 C 프로그램에서 사용할 수 없습니다.

다음 샘플에서는 C2733 오류가 생성 됩니다.

```
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```