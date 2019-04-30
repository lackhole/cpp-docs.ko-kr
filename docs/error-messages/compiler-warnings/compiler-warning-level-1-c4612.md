---
title: 컴파일러 경고(수준 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: ed5458fc52c1c9c9f12187095e4658204613d1a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406368"
---
# <a name="compiler-warning-level-1-c4612"></a>컴파일러 경고(수준 1) C4612

> 포함 파일 이름에 오류가 있습니다.

## <a name="remarks"></a>설명

파일 이름이 잘못되었거나 누락된 경우 **#pragma include_alias** 에서 이 경고가 발생합니다.

에 대 한 인수는 **#pragma include_alias** 문은 견적 폼을 사용할 수 있습니다 ("*filename*") 또는 꺾쇠 괄호 양식 (\<*filename*>), 둘 다 해야 하지만 동일한 형식을 사용 합니다.

## <a name="example"></a>예제

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```