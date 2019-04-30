---
title: 컴파일러 오류 C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: 5f9b60499fd3c3bd5f06834e3c4f6482031066d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406966"
---
# <a name="compiler-error-c2823"></a>컴파일러 오류 C2823

> typedef 템플릿이 잘못 되었습니다.

서식 파일에서 허용 되지 않는 `typedef` 정의 합니다.

## <a name="example"></a>예제

다음 샘플 C2823, 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```