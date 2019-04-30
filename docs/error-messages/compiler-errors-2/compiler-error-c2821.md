---
title: 컴파일러 오류 C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: 5c725d9648a7800c68a2fbff20e594a400c296c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208193"
---
# <a name="compiler-error-c2821"></a>컴파일러 오류 C2821

'operator new' 첫 번째 정식 매개 변수 'unsigned int' 이어야 합니다.

첫 번째 정식 매개 변수를 [new 연산자](../../standard-library/new-operators.md#op_new) 부호 없는 해야 `int`합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2821 오류가 생성 됩니다.

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```