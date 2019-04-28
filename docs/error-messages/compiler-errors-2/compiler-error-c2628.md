---
title: 컴파일러 오류 C2628
ms.date: 11/04/2016
f1_keywords:
- C2628
helpviewer_keywords:
- C2628
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
ms.openlocfilehash: 90df41ba8ae85e57e40848f8b50f4c1df7c7b541
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222925"
---
# <a name="compiler-error-c2628"></a>컴파일러 오류 C2628

'type1' 'type2' 뒤에 유효 하지 않은 (했는지를 ';'?)

세미콜론 누락 될 수 있습니다.

다음 샘플에서는 C2628 오류가 생성 됩니다.

```
// C2628.cpp
class CMyClass {}
int main(){}   // C2628 error
```

해결 방법:

```
// C2628b.cpp
class CMyClass {};
int main(){}
```