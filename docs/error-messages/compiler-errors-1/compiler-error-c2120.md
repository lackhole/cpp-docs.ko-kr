---
title: 컴파일러 오류 C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: 699a80b2cdb1de175c78efb918ba9389ec3695f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182862"
---
# <a name="compiler-error-c2120"></a>컴파일러 오류 C2120

' void' 형식도 사용할 수 없습니다.

`void` 형식은 다른 형식의 선언에 사용 됩니다.

다음 샘플에서는 C2120 오류가 생성 됩니다.

```
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```