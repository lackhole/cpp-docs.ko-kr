---
title: 컴파일러 오류 C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: f61281da23e46236e7fce496a4d89086e5d6c0ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165046"
---
# <a name="compiler-error-c2870"></a>컴파일러 오류 C2870

'name': 네임 스페이스 정의 다른 네임 스페이스 정의 내에서 파일 범위 또는 즉시 나타나야 합니다.

네임 스페이스를 정의한 `name` 잘못 됩니다. (모든 블록 및 클래스) 외부 파일 범위에서 네임 스페이스를 정의 해야 합니다 또는 다른 네임 스페이스 내에서 바로.

다음 샘플에서는 C2870 오류가 생성 됩니다.

```
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```