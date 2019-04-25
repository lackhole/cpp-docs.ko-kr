---
title: 컴파일러 오류 C3233
ms.date: 11/04/2016
f1_keywords:
- C3233
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
ms.openlocfilehash: 4a0cf849f7b87bd8d61b0ef087cf91d15669d719
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173836"
---
# <a name="compiler-error-c3233"></a>컴파일러 오류 C3233

'type': 제네릭 형식 매개 변수에 이미 제약 조건이 적용되었습니다.

제네릭 매개 변수를 둘 이상의 `where` 절에 포함할 수 없습니다.

다음 샘플에서는 C3233을 생성합니다.

```
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```