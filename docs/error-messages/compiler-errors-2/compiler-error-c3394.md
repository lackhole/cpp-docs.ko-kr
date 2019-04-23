---
title: 컴파일러 오류 C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: 826084d375c69ca289a858a29a12ae16874c1fbd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775430"
---
# <a name="compiler-error-c3394"></a>컴파일러 오류 C3394

제약 조건 절의 구문 오류: 형식이 필요한데 'identifier'가 있습니다.

제약 조건 형식이 잘못되었습니다.  자세한 내용은 [제네릭 형식 매개 변수에 대 한 제약 조건 (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3394를 생성합니다.

```
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```