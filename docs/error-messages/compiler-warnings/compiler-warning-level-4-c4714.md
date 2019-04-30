---
title: 컴파일러 경고(수준 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: ed94e5b716a697ec96d7fecac75433823c9a67e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395185"
---
# <a name="compiler-warning-level-4-c4714"></a>컴파일러 경고(수준 4) C4714

' function' 인라인이 아니라 __forceinline로 표시

지정된 된 함수를 인라인 확장 선택 했지만 컴파일러가 수행 하지 않은 인라인 처리 합니다.

하지만 `__forceinline` 보다 컴파일러에 보다 강력한 표시가 `__inline`인라인 처리, 컴파일러의 판단에 따라 계속 수행에서 혜택을 확인 하려면 없습니다 경험적 접근을 사용 하지만 인라인이 함수입니다.

일부 경우에 컴파일러는 인라인 처리 하지 않습니다 특정 함수 기계적 이유로 합니다. 예를 들어, 컴파일러는 인라인 처리 하지 않습니다.

- 두 SEH를 혼합 하는 경우 함수 및 C++ EH 합니다.

- 복사를 사용 하 여 일부 함수-GX EHs//eha 켜진 경우 값으로 전달 된 개체를 생성 합니다.

- -GX EHs//eha 켜진 경우 값으로 해제할 수 있는 개체를 반환 하는 함수입니다.

- -Og/Ox/O1/O2 없이 컴파일하는 경우 인라인 어셈블리로 함수입니다.

- 가변 인수 목록이 있는 함수입니다.

- 사용 하는 함수를 **시도** (C++ 예외 처리) 문입니다.

다음 샘플에서는 C4714 오류가 생성 됩니다.

```
// C4714.cpp
// compile with: /Ob1 /GX /W4
__forceinline void func1()
{
   try
   {
   }
   catch (...)
   {
   }
}

void func2()
{
   func1();   // C4714
}

int main()
{
}
```