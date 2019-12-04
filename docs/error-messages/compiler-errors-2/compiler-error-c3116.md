---
title: 컴파일러 오류 C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: d0c8e7cab936171f89b33c90b4134a97c40b2c81
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741185"
---
# <a name="compiler-error-c3116"></a>컴파일러 오류 C3116

' storage 지정자 ': 인터페이스 메서드에 대 한 저장소 클래스가 잘못 되었습니다.

인터페이스 메서드에 대 한 저장소 클래스로 `typedef`, `register`또는 `static`를 사용 했습니다. 이러한 저장소 클래스는 인터페이스 멤버에서 허용 되지 않습니다.

다음 샘플에서는 C3116를 생성 합니다.

```cpp
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```
