---
title: 컴파일러 경고(수준 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 3a56e58d9bec1034a55f4e588dbddd0dba03f348
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208029"
---
# <a name="compiler-warning-level-1-c4076"></a>컴파일러 경고(수준 1) C4076

> '*형식 한정자*': 형식을 사용 하 여 사용할 수 없습니다 '*typename*'

## <a name="remarks"></a>설명

형식 한정자를 인지 **서명** 하거나 **부호 없는**, 정수가 아닌 형식과 사용할 수 없습니다. *형식 한정자* 무시 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 C4076; 이 문제를 해결 하려면 제거 합니다 **부호 없는** 형식 한정자:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```