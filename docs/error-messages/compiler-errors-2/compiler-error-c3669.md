---
title: 컴파일러 오류 C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: 3b0ad3aa7395f5f423c8c36f547d4a0e2ad792c1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777105"
---
# <a name="compiler-error-c3669"></a>컴파일러 오류 C3669

'member': 재정의 지정자 'override' 정적 멤버 함수 또는 생성자에서 사용할 수 없습니다

재정의 잘못 지정 되었습니다. 자세한 내용은 [명시적으로 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3669를 생성합니다.

```
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```