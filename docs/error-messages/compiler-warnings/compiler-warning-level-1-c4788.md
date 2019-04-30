---
title: 컴파일러 경고(수준 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: c51a4409c2a3028823462539343654b5eac365d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187207"
---
# <a name="compiler-warning-level-1-c4788"></a>컴파일러 경고(수준 1) C4788

'identifier': 식별자 'number' 자로 잘렸습니다.

컴파일러는 함수 이름을 사용할 수 있는 최대 길이 제한 합니다. 일부 텍스트를 사용 하 여 함수 이름을 추가 하 여 작은 함수 이름을 형성 컴파일러 funclets EH/SEH 코드를 생성할 때 "__catch를 선택 예를 들어", "\__unwind", 또는 다른 문자열입니다.

결과 작은 함수 이름이 너무 길어질 수 있습니다 및 컴파일러를 잘라 C4788를 생성 합니다.

이 경고를 해결 하려면 원래 함수 이름을 단축 합니다. 함수는 경우는 C++ 템플릿 함수 또는 메서드 이름 부분에 대 한 typedef를 사용 합니다. 예를 들어:

```
C1<x, y, z<T>>::C2<a,b,c>::f
```

으로 바꿀 수 있습니다.

```
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

이 경고는 x64 에서만 발생 컴파일러.