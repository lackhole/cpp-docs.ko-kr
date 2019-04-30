---
title: 컴파일러 경고(수준 2) C4309
ms.date: 11/04/2016
f1_keywords:
- C4309
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
ms.openlocfilehash: 41184571dc07213c796c039170966a0c7150bd45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402478"
---
# <a name="compiler-warning-level-2-c4309"></a>컴파일러 경고(수준 2) C4309

'conversion': 상수 값 잘림

형식 변환으로 할당 된 공간을 초과 하는 상수입니다. 상수에 대 한 더 큰 형식을 사용 해야 합니다.

다음 샘플에서는 C4309 오류가 생성 됩니다.

```
// C4309.cpp
// compile with: /W2
int main()
{
   char c = 128;   // C4309
}
```