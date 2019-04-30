---
title: 컴파일러 경고(수준 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: 55512bf28c8c20512d0d245810d3e5c1fec36939
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402036"
---
# <a name="compiler-warning-level-3-c4334"></a>컴파일러 경고(수준 3) C4334

'operator': 32 비트 시프트의 결과가 암시적으로 64 비트로 변환 (64 비트 시프트를 사용 했습니다.)

32 비트 시프트의 결과가 64 비트 및 64 비트 시프트를 의도 된 컴파일러 의심 암시적으로 변환 되었습니다.  이 경고를 해결 하려면 64 비트 시프트를 사용 하거나 64 비트를 시프트 결과 명시적으로 캐스팅 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4334 오류가 발생 합니다.

```
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```