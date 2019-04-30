---
title: 컴파일러 오류 C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: 98b43a2f3c0888fc385226cd80889b9911c84690
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227916"
---
# <a name="compiler-error-c2757"></a>컴파일러 오류 C2757

'symbol': 이름이 같은 기호가 이미 및 네임 스페이스 이름으로이 이름은 사용할 수 있으므로

네임 스페이스 식별자로 현재 컴파일에서 사용 되는 기호 참조 된 어셈블리에서 이미 사용 중입니다.

다음 샘플에서는 C2757를 생성합니다.

```
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

그리고

```
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
