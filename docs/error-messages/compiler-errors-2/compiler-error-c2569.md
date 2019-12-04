---
title: 컴파일러 오류 C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: 7299fe8daa1fa0fc6e1291bf8c683b33235e8bbf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755527"
---
# <a name="compiler-error-c2569"></a>컴파일러 오류 C2569

' EnumOrUnion ': 열거형/공용 구조체를 기본 클래스로 사용할 수 없습니다.

지정 된 공용 구조체 또는 열거형에서 형식을 파생 시켜야 하는 경우 공용 구조체 또는 열거형을 클래스나 구조체로 변경 합니다.

다음 샘플에서는 C2569를 생성 합니다.

```cpp
// C2569.cpp
// compile with: /c
union ubase {};
class cHasPubUBase : public ubase {};   // C2569
// OK
struct sbase {};
class cHasPubUBase : public sbase {};
```
