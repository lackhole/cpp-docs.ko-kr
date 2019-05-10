---
title: 컴파일러 오류 C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 788f03e4364404ad5c30b7edcba8b743c7f201ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152425"
---
# <a name="compiler-error-c3846"></a>컴파일러 오류 C3846

'symbol': 'assembly2'에서 기호를 가져올 수 없습니다: 'symbol' 어셈블리가 'assembly1'에서 이미 가져온 대로

참조 된 어셈블리에서 이전에 가져온 참조 된 어셈블리에서 기호를 가져올 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3846 오류가 생성 됩니다.

```
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

하 고이 컴파일합니다.

```
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
