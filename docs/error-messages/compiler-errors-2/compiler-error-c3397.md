---
title: 컴파일러 오류 C3397
ms.date: 11/04/2016
f1_keywords:
- C3397
helpviewer_keywords:
- C3397
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
ms.openlocfilehash: c6ca48eb53cf1c6d661a201fa8c4d2539669b9bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58772854"
---
# <a name="compiler-error-c3397"></a>컴파일러 오류 C3397

기본 인수에서는 집합체 초기화가 허용되지 않습니다.

배열이 잘못 선언되었습니다.  참조 [배열](../../extensions/arrays-cpp-component-extensions.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3397을 생성합니다.

```
// C3397.cpp
// compile with: /clr
// /clr /c
void Func(array<int> ^p = gcnew array<int> { 1, 2, 3 });   // C3397
void Func2(array<int> ^p = gcnew array<int> (3));   // OK

int main() {
   array<int> ^p = gcnew array<int> { 1, 2, 3};   // OK
}
```