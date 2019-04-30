---
title: 컴파일러 경고 (수준 1) C4079
ms.date: 11/04/2016
f1_keywords:
- C4079
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
ms.openlocfilehash: 8f9a9e05ab2a65ad954f9928f7b9fab0e7fee9cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207527"
---
# <a name="compiler-warning-level-1-c4079"></a>컴파일러 경고 (수준 1) C4079

예기치 않은 'token' 토큰입니다.

예기치 않은 구분 기호 토큰을 pragma 인수 목록에 발생합니다. 나머지 pragma가 무시 되었습니다.

다음 샘플에서는 C4079 오류가 생성 됩니다.

```
// C4079.cpp
// compile with: /W1
#pragma warning(disable : 4081)
#pragma pack(c,16)   // C4079

int main() {
}
```