---
title: 컴파일러 경고(수준 3) C4161
ms.date: 08/27/2018
f1_keywords:
- C4161
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
ms.openlocfilehash: e1bbc949c298a7cfb6c3a3a061616db3dc4730f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402270"
---
# <a name="compiler-warning-level-3-c4161"></a>컴파일러 경고(수준 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>pragma *pragma*(팝...): 푸시 횟수 보다 팝

## <a name="remarks"></a>설명

소스 코드에서 pragma *pragma*에 대한 팝 횟수가 푸시 횟수보다 하나 더 많으므로 스택이 예상대로 동작하지 않을 수 있습니다. 경고를 방지하려면 팝 횟수가 푸시 횟수를 초과하지 않도록 합니다.

## <a name="example"></a>예제

다음 예제에서는 C4161을 생성합니다.

```cpp
// C4161.cpp
// compile with: /W3 /LD
#pragma pack(push, id)
#pragma pack(pop, id)
#pragma pack(pop, id)   // C4161, an extra pop

#pragma bss_seg(".my_data1")
int j;

#pragma bss_seg(push, stack1, ".my_data2")
int l;

#pragma bss_seg(pop, stack1)
int m;

#pragma bss_seg(pop, stack1)   // C4161
```