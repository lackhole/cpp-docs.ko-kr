---
title: 컴파일러 경고 (수준 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: ebebfe9994be3dd136e3924cb2aea60c0c901926
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051626"
---
# <a name="compiler-warning-level-3-c4334"></a>컴파일러 경고 (수준 3) C4334

' operator ': 32 비트 시프트 결과가 64 비트로 암시적으로 변환 됩니다 (64 비트 이동 의도?).

32 비트 시프트 결과는 명시적으로 64 비트로 변환 되었으며 컴파일러는 64 비트 시프트를 의도 한 것으로 의심 합니다.  이 경고를 해결 하려면 64 비트 시프트를 사용 하거나 명시적으로 시프트 결과를 64 비트로 캐스팅 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4334를 생성 합니다.

```cpp
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```