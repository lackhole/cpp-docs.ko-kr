---
title: 컴파일러 오류 C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 379bcc7f37ff8942e4e45c6a6188438400937875
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187908"
---
# <a name="compiler-error-c2348"></a>컴파일러 오류 C2348

'type name': 포함 IDL에서 내보낼 수 없습니다, C 스타일 집합체가 아닙니다.

배치 하는 `struct` .idl 파일의는 [내보내기](../../windows/export.md) 특성을는 `struct` 데이터만 포함 해야 합니다.

다음 샘플에서는 C2348를 생성합니다.

```
// C2348.cpp
// C2348 error expected
[ module(name="SimpleMidlTest") ];

[export]
struct Point {
   // Delete the following two lines to resolve.
   Point() : m_i(0), m_j(0) {}
   Point(int i, int j) : m_i(i), m_j(j) {}

   int m_i;
   int m_j;
};
```