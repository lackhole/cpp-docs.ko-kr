---
title: 컴파일러 오류 C2878
ms.date: 11/04/2016
f1_keywords:
- C2878
helpviewer_keywords:
- C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
ms.openlocfilehash: f4570b7a2746386c66f8aa783f9270efb15d4765
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378905"
---
# <a name="compiler-error-c2878"></a>컴파일러 오류 C2878

'name': 네임 스페이스 또는 클래스 이름이 없습니다.

네임 스페이스 또는 정의 되지 않은 클래스를 참조를 했습니다.

다음 샘플에서는 C2878 오류가 생성 됩니다.

```
// C2878.cpp
// compile with: /c
namespace A {}
namespace B = C;   // C2878 namespace C doesn't exist
namespace B = A;
```