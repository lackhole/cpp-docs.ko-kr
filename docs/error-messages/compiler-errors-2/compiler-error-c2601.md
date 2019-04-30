---
title: 컴파일러 오류 C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: f18819e5f078cb85121160af1d4a3fc24a365a68
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215587"
---
# <a name="compiler-error-c2601"></a>컴파일러 오류 C2601

'function': 지역 함수 정의가 올바르지 않습니다.

코드는 함수 내에서 함수를 정의 하려고 시도 합니다.

또는 C2601 오류의 위치 앞에 소스 코드에서 하는 추가 중괄호 있을 수 있습니다.

다음 샘플에서는 C2601 오류가 생성 됩니다.

```
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```