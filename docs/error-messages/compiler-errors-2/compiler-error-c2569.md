---
title: 컴파일러 오류 C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: 1344bd8bde532d2e813ca03e173b995e935c76b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243761"
---
# <a name="compiler-error-c2569"></a>컴파일러 오류 C2569

'EnumOrUnion': 열거형/공용 구조체를 기본 클래스로 사용할 수 없습니다

형식으로 지정 된 공용 구조체 또는 열거형에서 파생 되어야 하는 경우 클래스 또는 구조체에는 공용 구조체 또는 열거형을 변경 합니다.

다음 샘플에서는 C2569 오류가 생성 됩니다.

```
// C2569.cpp
// compile with: /c
union ubase {};
class cHasPubUBase : public ubase {};   // C2569
// OK
struct sbase {};
class cHasPubUBase : public sbase {};
```