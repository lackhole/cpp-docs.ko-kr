---
title: 컴파일러 경고(수준 1) C4537
ms.date: 08/27/2018
f1_keywords:
- C4537
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
ms.openlocfilehash: 2f97be4e1aaa5143df685cb95935d350e6f02534
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161084"
---
# <a name="compiler-warning-level-1-c4537"></a>컴파일러 경고(수준 1) C4537

> '*개체*': '*연산자*' 비 UDT 형식에 적용

## <a name="remarks"></a>설명

참조 개체 (사용자 정의 형식)가 필요 합니다. 여기서 전달 되었습니다. 참조 개체는 아닌 인라인 어셈블러 코드로 차이 만들 수 있습니다. 컴파일러 생성 코드 처럼 *개체* 인스턴스.

## <a name="example"></a>예제

다음 샘플 C4537 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C4537.cpp
// compile with: /W1 /c
// processor: x86
struct S {
    int member;
};

void f1(S &s) {
    __asm mov eax, s.member;   // C4537
    // try the following code instead
    // or, make the declaration "void f1(S s)"
    /*
    mov eax, s
    mov eax, [eax]s.member
    */
}
```