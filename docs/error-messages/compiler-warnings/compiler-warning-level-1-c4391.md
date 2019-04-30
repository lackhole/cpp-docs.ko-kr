---
title: 컴파일러 경고(수준 1) C4391
ms.date: 11/04/2016
f1_keywords:
- C4391
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
ms.openlocfilehash: d9d1cebe08a6a163d76271ab001ec91b7cee82a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386462"
---
# <a name="compiler-warning-level-1-c4391"></a>컴파일러 경고(수준 1) C4391

'서명': 내장 함수에 대 한 잘못 된 반환 형식 'type' 예상

함수 선언에는 컴파일러 내장 함수에 잘못 된 반환 형식을 했습니다. 결과 이미지는 제대로 실행 되지 않을 수 있습니다.

이 경고를 해결 하려면 선언을 수정 하거나 삭제할 선언 고 #include 적절 한 헤더 파일입니다.

다음 샘플에서는 C4391 오류가 생성 됩니다.

```
// C4391.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_load_ss(float *p);   // C4391

#ifdef  __cplusplus
}
#endif

int main()
{
}
```