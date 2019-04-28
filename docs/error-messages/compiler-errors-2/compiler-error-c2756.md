---
title: 컴파일러 오류 C2756
ms.date: 11/04/2016
f1_keywords:
- C2756
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
ms.openlocfilehash: ccbbb7875fdae48fd00f87f9a63f3764c143daae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227786"
---
# <a name="compiler-error-c2756"></a>컴파일러 오류 C2756

'template type' : 부분 특수화에는 기본 템플릿 인수를 사용할 수 없습니다.

부분 특수화에 대한 템플릿에는 기본 인수가 포함될 수 없습니다.

다음 샘플에서는 C2756을 생성하고 해결 방법을 보여 줍니다.

```
// C2756.cpp
template <class T>
struct S {};

template <class T=int>
// try the following line instead
// template <class T>
struct S<T*> {};   // C2756
```