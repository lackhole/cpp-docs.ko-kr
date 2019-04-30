---
title: 컴파일러 경고(수준 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: c7facdde54b44ba2ce07db0447b251d7014f76c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324586"
---
# <a name="compiler-warning-level-4-c4690"></a>컴파일러 경고(수준 4) C4690

> \[ emitidl (pop)]: 푸시 횟수 보다 팝

## <a name="remarks"></a>설명

[emitidl](../../windows/emitidl.md) 특성을 넣은 횟수보다 꺼낸 횟수가 한 번 더 많습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4690을 생성합니다. 이 문제를 해결 하려면 특성 푸시됩니다 횟수 만큼 정확 하 게 팝 되 고 있는지를 확인 합니다.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
