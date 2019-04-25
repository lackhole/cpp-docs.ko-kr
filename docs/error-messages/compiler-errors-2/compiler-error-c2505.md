---
title: 컴파일러 오류 C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: bf5ffb9b6bad3db1d264941a6aefa391be521c98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165043"
---
# <a name="compiler-error-c2505"></a>컴파일러 오류 C2505

'symbol': '__declspec(modifer)' 전역 개체 또는 정적 데이터 멤버의 선언 또는 정의에 적용 될 수 있습니다

`__declspec` 전역 범위에만 사용 하도록 설계 된 한정자가 함수에 사용 되었습니다.

자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.

다음 샘플에서는 C2505 오류가 생성 됩니다.

```
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```