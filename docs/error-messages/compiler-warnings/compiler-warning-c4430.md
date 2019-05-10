---
title: 컴파일러 경고 C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: fe765fa49b9aa11667e1eac4a9cfed54bb84fd8f
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447869"
---
# <a name="compiler-warning-c4430"></a>컴파일러 경고 C4430

형식 지정자가 없습니다. int로 가정합니다. 참고: C++기본 int를 지원 하지 않습니다.

이 오류는 Visual Studio 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 모든 선언 명시적으로 형식을 지정 해야 합니다. int가 더 이상 사용 됩니다.

C4430은 항상 오류로 실행 됩니다.  사용 하 여이 경고를 해제할 수 있습니다 합니다 `#pragma warning` 나 **/wd**; 참조 [경고](../../preprocessor/warning.md) 또는 [/w, / w0, / w1, / w2, / w3, / w4, / w1, / w2, / w3, / w4, /Wall, /wd, / we, /wo, /Wv, /WX (경고 수준)](../../build/reference/compiler-option-warning-level.md)자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C4430을 생성합니다.

```
// C4430.cpp
// compile with: /c
struct CMyClass {
   CUndeclared m_myClass;  // C4430
   int m_myClass;  // OK
};

typedef struct {
   POINT();   // C4430
   // try the following line instead
   // int POINT();
   unsigned x;
   unsigned y;
} POINT;
```