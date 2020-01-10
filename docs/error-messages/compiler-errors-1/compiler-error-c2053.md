---
title: 컴파일러 오류 C2053
ms.date: 11/04/2016
f1_keywords:
- C2053
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
ms.openlocfilehash: a74e8104ec55e465875846b48186b9abdcb0f2f0
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302070"
---
# <a name="compiler-error-c2053"></a>컴파일러 오류 C2053

' identifier ': 와이드 문자열이 일치 하지 않습니다.

와이드 문자열은 호환 되지 않는 형식에 할당 됩니다.

다음 샘플에서는 C2053를 생성 합니다.

```c
// C2053.c
int main() {
   char array[] = L"Rika";   // C2053
}
```
