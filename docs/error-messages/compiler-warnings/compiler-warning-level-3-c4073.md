---
title: 컴파일러 경고 (수준 3) C4073
ms.date: 11/04/2016
f1_keywords:
- C4073
helpviewer_keywords:
- C4073
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
ms.openlocfilehash: db39f76f9bfdd46c300ea6e3738a63b636fe0a03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402335"
---
# <a name="compiler-warning-level-3-c4073"></a>컴파일러 경고 (수준 3) C4073

이니셜라이저가 라이브러리 초기화 영역

타사 라이브러리 개발자에 의해 지정 되는 라이브러리 초기화 영역을 사용 해야 하는 전용 [#pragma init_seg](../../preprocessor/init-seg.md)합니다. 다음 샘플에서는 C4073 오류가 생성 됩니다.

```
// C4073.cpp
// compile with: /W3
#pragma init_seg(lib)   // C4073

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```