---
title: 컴파일러 오류 C2753
ms.date: 11/04/2016
f1_keywords:
- C2753
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
ms.openlocfilehash: e13c45cec99e60d8aec7dcc3db8e5a4813ea7de9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228785"
---
# <a name="compiler-error-c2753"></a>컴파일러 오류 C2753

'*템플릿*': 부분 특수화는 기본 템플릿 인수 목록이 일치할 수 없습니다.

템플릿 인수 목록에 매개 변수 목록에 일치 하는 경우 컴파일러는 동일한 템플릿으로 처리 합니다. 같은 서식 파일을 두 번 정의할 수 없습니다.

## <a name="example"></a>예제

다음 샘플 C2753 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C2753.cpp
// compile with: cl /c C2753.cpp
template<class T>
struct A {};

template<class T>
struct A<T> {};   // C2753
// try the following line instead
// struct A<int> {};

template<class T, class U, class V, class W, class X>
struct B {};
```