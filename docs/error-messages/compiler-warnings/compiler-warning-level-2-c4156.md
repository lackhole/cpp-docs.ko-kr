---
title: 컴파일러 경고 (수준 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 7d9a4ed09f026267e2c0f37fbbe4550ecd668dfc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350467"
---
# <a name="compiler-warning-level-2-c4156"></a>컴파일러 경고 (수준 2) C4156

'delete';' 배열 형식을 사용 하지 않고 배열 식 삭제 배열 형식이 대체 됩니다.

배열이 아닌 형태의 **삭제** 배열을 삭제할 수 없습니다. 컴파일러가 변환 **삭제** 배열 형식으로 합니다.

이 경고는 Microsoft 확장 (/Ze)에 발생합니다.

## <a name="example"></a>예제

```
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```