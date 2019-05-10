---
title: 컴파일러 오류 C2998
ms.date: 11/04/2016
f1_keywords:
- C2998
helpviewer_keywords:
- C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
ms.openlocfilehash: 16a3319e71d465082120cbc58e3c7c6b916be80f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393612"
---
# <a name="compiler-error-c2998"></a>컴파일러 오류 C2998

'identifier': 템플릿 정의일 수 없습니다.

컴파일러에서 템플릿 정의에 사용되는 구문을 처리할 수 없습니다.

다음 샘플에서는 C2998을 생성합니다.

```
// C2998.cpp
// compile with: /c
template <class T> int x = 1018; // C2998
```