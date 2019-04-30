---
title: 컴파일러 경고(수준 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 067d1aef41280f4d14fe799e4f4ee26a9f1b9f5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401022"
---
# <a name="compiler-warning-level-4-c4239"></a>컴파일러 경고(수준 4) C4239

비표준 확장이 사용 됨: 'token': 'type'에서 'type'로 변환

하 여이 형식으로 변환할 수 없습니다는 C++ standard 하지만 대체가 확장으로 여기입니다. 이 경고 뒤에 항상 하나 이상의 줄을 위반 하는 언어 규칙을 설명 하는 설명.

## <a name="example"></a>예제

다음 샘플 C4239를 생성합니다.

```
// C4239.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

void func(void) {
   C & rC = C();   // C4239
   const C & rC2 = C();   // OK
   rC2;
}
```

## <a name="example"></a>예제

정수 계열 형식에서 열거형 형식 변환할 엄격 하 게 허용 되지 않습니다.

다음 샘플 C4239를 생성합니다.

```
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```