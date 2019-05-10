---
title: 컴파일러 경고(수준 2) C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: 96e1077ce3c9e60823a11aa41719738265ee703b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345380"
---
# <a name="compiler-warning-level-2-c4285"></a>컴파일러 경고(수준 2) C4285

반환 형식이 'identifier:: operator->'가 중 위 표기법을 사용 하 여 적용할 경우 재귀적

지정 된 **operator-> ()** 함수 형식을 반환할 수 없습니다. 정의 또는 정의 된 형식에 대 한 참조입니다.

다음 샘플에서는 C4285 오류가 생성 됩니다.

```
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```