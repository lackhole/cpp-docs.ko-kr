---
title: 컴파일러 오류 C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 7bded618c481e59f60c5528510c757dec7226acc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759999"
---
# <a name="compiler-error-c2348"></a>컴파일러 오류 C2348

' type name ': C 스타일 집합체가 아니므로 포함 IDL에서 내보낼 수 없습니다.

[내보내기](../../windows/export.md) 특성을 사용 하 여 `struct`을 .idl 파일에 저장 하려면 `struct` 데이터만 포함 해야 합니다.

다음 샘플에서는 C2348를 생성 합니다.

```cpp
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
