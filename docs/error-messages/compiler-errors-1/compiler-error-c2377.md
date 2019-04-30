---
title: 컴파일러 오류 C2377
ms.date: 11/04/2016
f1_keywords:
- C2377
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
ms.openlocfilehash: b4789469fe27dafb2fb13bf3db085958db8d1478
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393729"
---
# <a name="compiler-error-c2377"></a>컴파일러 오류 C2377

'identifier': 재정의. 다른 기호를 사용하여 형식 정의를 오버로드할 수 없습니다.

`typedef` 식별자가 다시 정의되었습니다.

다음 샘플에서는 C2377을 생성합니다.

```
// C2377.cpp
// compile with: /c
typedef int i;
int i;   // C2377
int j;   // OK
```