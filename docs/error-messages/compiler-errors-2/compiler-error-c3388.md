---
title: 컴파일러 오류 C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: 3b56aae115b1a1721f3f8a8688e36b25edc7f33f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776732"
---
# <a name="compiler-error-c3388"></a>컴파일러 오류 C3388

'type': 제약 조건으로 사용할 수 없습니다. 구문 분석을 계속하기 위해 'ref class'로 간주합니다.

제약 조건이 제네릭 형식에 지정되었지만 제약 조건을 올바르게 지정하지 않았습니다. 참조 [제네릭 형식 매개 변수에 대 한 제약 조건 (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 에 대 한 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3388을 생성합니다.

```
// C3388.cpp
// compile with: /clr /c
interface class AA {};

generic <class T>
where T : interface class   // C3388
ref class C {};

// OK
generic <class T>
where T : AA
ref class D {};
```