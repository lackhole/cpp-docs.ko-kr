---
title: 컴파일러 오류 C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: fcf2bbb01f2aac668ff52884a6ccfb36c66aa89d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395380"
---
# <a name="compiler-error-c2785"></a>컴파일러 오류 C2785

'declaration1' 및 'declaration2'는 다른 반환 형식

기본 함수 템플릿은의 반환 형식에서 함수 템플릿 특수화의 반환 형식이 서로 다릅니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 일관성에 대 한 함수 템플릿의 모든 특수화를 확인 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2785를 생성합니다.

```
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```