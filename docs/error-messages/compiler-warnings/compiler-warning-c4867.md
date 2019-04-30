---
title: 컴파일러 경고 C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: 9fa9b382b42a2fb8ba72fd9744c612af5dd598d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311074"
---
# <a name="compiler-warning-c4867"></a>컴파일러 경고 C4867

'function': 함수 호출 인수 목록이 없습니다. '호출'을 사용 하 여 멤버에 대 한 포인터를 만들려면

멤버 함수에 대 한 포인터를 올바르게 초기화 되었습니다.

이 경고는 시각적 개체에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 됩니다 C++ 2005: 멤버 포인터 규칙이 향상 되었습니다.  Visual 이전에 컴파일된 코드 C++ 2005 C4867 이제 생성 됩니다.

항상이 경고는 오류로 발생 됩니다. [warning](../../preprocessor/warning.md) pragma를 사용하여 이 경고를 사용하지 않도록 설정합니다. C4867 및 MFC/ATL에 대 한 자세한 내용은 참조 하세요. [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning)합니다.

## <a name="example"></a>예제

다음 샘플 C4867를 생성합니다.

```
// C4867.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b = {f};   // C4867
      B b2 = {&A::f};   // OK
   }
};
```