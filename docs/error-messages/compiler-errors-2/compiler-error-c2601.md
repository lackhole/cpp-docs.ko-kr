---
title: 컴파일러 오류 C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: 87b5afe2133bb737a8f9c855b0652c2f50ca27ec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740522"
---
# <a name="compiler-error-c2601"></a>컴파일러 오류 C2601

' function ': 지역 함수 정의가 잘못 되었습니다.

코드는 함수 내에서 함수를 정의 하려고 합니다.

또는 C2601 오류의 위치 앞에 소스 코드에 추가 중괄호가 있을 수 있습니다.

다음 샘플에서는 C2601를 생성 합니다.

```cpp
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```
