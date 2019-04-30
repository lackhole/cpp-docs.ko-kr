---
title: 컴파일러 오류 C2117
ms.date: 11/04/2016
f1_keywords:
- C2117
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
ms.openlocfilehash: 2f6a1e26972f093e50c5e655935f750195ab7d3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338573"
---
# <a name="compiler-error-c2117"></a>컴파일러 오류 C2117

'identifier': 배열 범위 오버플로입니다

배열에 이니셜라이저가 너무 많습니다.

- 배열 요소와 이니셜라이저의 크기 및 수량이 일치 하지 않습니다.

- 문자열에 null 종결자에 대 한 공간이 없습니다.

다음 샘플에서는 C2117 오류가 생성 됩니다.

```
// C2117.cpp
int main() {
   char abc[4] = "abcd";   // C2117
   char def[4] = "abd";   // OK
}
```