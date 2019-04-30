---
title: 컴파일러 경고(수준 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: 8eca942de1d2f78f5e42d4aac7e2441789a01862
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401165"
---
# <a name="compiler-warning-level-4-c4212"></a>컴파일러 경고(수준 4) C4212

비표준 확장이 사용 됨: 줄임표 (...)를 사용 하는 함수 선언

함수 프로토타입은 인수의 변수 번호입니다. 함수 정의 되지 않습니다.

다음 샘플에서는 C4212 오류가 생성 됩니다.

```
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```