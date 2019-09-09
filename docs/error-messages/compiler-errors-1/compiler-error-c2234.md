---
title: 컴파일러 오류 C2234
ms.date: 11/04/2016
f1_keywords:
- C2234
helpviewer_keywords:
- C2234
ms.assetid: cfa42458-c803-4717-a017-9eca1c0cbfb0
ms.openlocfilehash: 16cc09f43f8705452c207e5218f4cc274557e825
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741141"
---
# <a name="compiler-error-c2234"></a>컴파일러 오류 C2234

' name ': 참조 배열이 잘못 되었습니다.

참조에 대 한 포인터는 허용 되지 않으므로 참조 배열을 사용할 수 없습니다.

다음 샘플에서는 C2234를 생성 합니다.

```
// C2234.cpp
int main() {
   int i = 0, j = 0, k = 0, l = 0;
   int &array[4] = {i,j,k,l};   // C2234
   int array2[4] = {i,j,k,l};   // OK
}
```