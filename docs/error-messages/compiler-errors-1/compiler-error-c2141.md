---
title: 컴파일러 오류 C2141
ms.date: 11/04/2016
f1_keywords:
- C2141
helpviewer_keywords:
- C2141
ms.assetid: 10cf770f-0500-4220-ac90-a863b7ea5fe6
ms.openlocfilehash: 89395fa3419d79fa4dec3fecf9acfc681590d825
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353568"
---
# <a name="compiler-error-c2141"></a>컴파일러 오류 C2141

배열 크기 오버플로

배열에는 2GB 한도가 초과합니다. 배열의 크기를 줄입니다.

## <a name="example"></a>예제

다음 샘플 C2141을 생성합니다.

```
// C2141.cpp
// processor: IPF
class A {
   short m_n;
};

int main()
{
   A* pA = (A*)(-1);
   pA = new A[0x8000000000000001];   // C2141

   A* pA2 = (A*)(-1);
   pA2 = new A[0x80000000000000F];   // OK
}
```