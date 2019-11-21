---
title: 컴파일러 경고 (수준 1) C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 9992032c71798f604b5a45a1b48c1266067b2acb
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966292"
---
# <a name="compiler-warning-level-1-c4518"></a>컴파일러 경고 (수준 1) C4518

' 지정자 ': 예기치 않은 저장소 클래스 또는 형식 지정자입니다. 무시

다음 샘플에서는 C4518를 생성 합니다.

```cpp
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```