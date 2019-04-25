---
title: 컴파일러 경고(수준 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 892e6c37e54a868be48ced35354a1096aa7bf9d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160746"
---
# <a name="compiler-warning-level-1-c4526"></a>컴파일러 경고(수준 1) C4526

'function': 정적 멤버 함수는 가상 함수를 재정의할 수 없습니다 ' 무시 가상 function'override 가상 함수가 숨겨집니다.

정적 멤버 함수는 가상 및 정적 멤버 함수는 가상 함수를 재정의 하는 조건을 충족 합니다.

다음 코드에서는 C4526 오류가 생성 됩니다.

```
// C4526.cpp
// compile with: /W1 /c
// C4526 expected
struct myStruct1 {
   virtual void __stdcall func( int ) = 0;
};

struct myStruct2: public myStruct1 {
   static void __stdcall func( int );
};
```

다음은 가능한 해결 방법입니다.

- 함수는 기본 클래스 가상 함수를 재정의 하려고 했던, static 지정자를 제거 합니다.

- 함수는 정적 멤버 함수를 사용 된 경우 이름을 기본 클래스 가상 함수를 사용 하 여 충돌 하지 않도록 합니다.