---
title: 컴파일러 오류 C3207
ms.date: 11/04/2016
f1_keywords:
- C3207
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
ms.openlocfilehash: 51873e089499e42f4ddeb97c95e3f18416df447c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402712"
---
# <a name="compiler-error-c3207"></a>컴파일러 오류 C3207

'function': 'arg'에 대한 템플릿 인수가 잘못되었습니다. 클래스 템플릿이 필요합니다.

템플릿 함수가 템플릿 인수를 사용하도록 정의되어 있습니다. 그러나 템플릿 형식 인수가 전달되었습니다.

다음 샘플에서는 C3207을 생성합니다.

```
// C3207.cpp
template <template <class T> class TT>
void f(){}

template <class T>
struct S
{
};

void f1()
{
   f<S<int> >();   // C3207
   // try the following line instead
   // f<S>();
}
```