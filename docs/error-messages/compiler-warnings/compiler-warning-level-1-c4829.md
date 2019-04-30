---
title: 컴파일러 경고(수준 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: 1afb29b10352150cac2969849979fb5b5e2b8719
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378481"
---
# <a name="compiler-warning-level-1-c4829"></a>컴파일러 경고(수준 1) C4829

main 함수에 대한 매개 변수가 잘못된 것 같습니다. 고려 ' intmain (platform:: array\<platform:: string ^ > ^ argv)'

main과 같은 특정 함수는 참조 형식 매개 변수를 사용할 수 없습니다. 컴파일은 성공하지만 결과 이미지가 실행되지 않을 수 있습니다.

다음 샘플에서는 C4829를 생성합니다.

```
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829
```