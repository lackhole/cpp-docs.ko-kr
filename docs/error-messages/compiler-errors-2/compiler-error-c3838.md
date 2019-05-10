---
title: 컴파일러 오류 C3838
ms.date: 11/04/2016
f1_keywords:
- C3838
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
ms.openlocfilehash: c8664c9df837d44ab6e356d54ff9e35c3776778a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208085"
---
# <a name="compiler-error-c3838"></a>컴파일러 오류 C3838

'type'에서 명시적으로 상속할 수 없습니다.

지정 된 `type` 클래스에서 기본 클래스로 작동할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3838 오류가 생성 됩니다.

```
// C3838a.cpp
// compile with: /clr /c
public ref class B : public System::Enum {};   // C3838
```
