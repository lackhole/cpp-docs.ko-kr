---
title: 컴파일러 오류 C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: 314b75a9d0ab8cde2886a7466fa0f95b5bbdd8f1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777213"
---
# <a name="compiler-error-c3299"></a>컴파일러 오류 C3299

'member_function': 제약 조건을 지정할 수 없습니다. 제약 조건이 기본 메서드에서 상속되었습니다.

제네릭 멤버 함수를 재정의하는 경우 제약 조건 절을 지정할 수 없습니다(제약 조건 반복은 제약 조건이 상속되지 않음을 나타냄).

재정의하는 제네릭 함수의 제약 조건 절이 상속됩니다.

자세한 내용은 [제네릭 형식 매개 변수에 대 한 제약 조건 (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3299를 생성합니다.

```
// C3299.cpp
// compile with: /clr /c
public ref struct R {
   generic<class T>
   where T : R
   virtual void f();
};

public ref struct S : R {
   generic<class T>
   where T : R   // C3299
   virtual void f() override;
};
```