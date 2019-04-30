---
title: 컴파일러 경고(수준 4) C4214
ms.date: 11/04/2016
f1_keywords:
- C4214
helpviewer_keywords:
- C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
ms.openlocfilehash: 31711d3709b7c2ae3658d760f538ea9e841d33a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401126"
---
# <a name="compiler-warning-level-4-c4214"></a>컴파일러 경고(수준 4) C4214

비표준 확장이 사용 됨: 비트 필드 형식이 int

기본 Microsoft 확장명 (/Ze)를 사용 하 여 모든 정수 형식의 비트 필드 구조체 멤버 수 있습니다.

## <a name="example"></a>예제

```
// C4214.c
// compile with: /W4
struct bitfields
{
   unsigned short j:4;  // C4214
};

int main()
{
}
```

이러한 비트 필드를 ANSI 호환성 올바르지 않습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).