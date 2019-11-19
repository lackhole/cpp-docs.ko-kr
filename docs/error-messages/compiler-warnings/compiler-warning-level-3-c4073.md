---
title: 컴파일러 경고 (수준 3) C4073
ms.date: 11/04/2016
f1_keywords:
- C4073
helpviewer_keywords:
- C4073
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
ms.openlocfilehash: af9f8fc7323fab8c737e7a63cea20809c9182ad9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051920"
---
# <a name="compiler-warning-level-3-c4073"></a>컴파일러 경고 (수준 3) C4073

이니셜라이저가 라이브러리 초기화 영역에 있습니다.

타사 라이브러리 개발자만 [#pragma init_seg](../../preprocessor/init-seg.md)지정 된 라이브러리 초기화 영역을 사용 해야 합니다. 다음 샘플에서는 C4073를 생성 합니다.

```cpp
// C4073.cpp
// compile with: /W3
#pragma init_seg(lib)   // C4073

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```