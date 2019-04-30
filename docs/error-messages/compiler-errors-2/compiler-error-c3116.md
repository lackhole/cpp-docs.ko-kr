---
title: 컴파일러 오류 C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: 3f587bc677d64bda0fb5eea0b7ebc8d5761a2e75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376070"
---
# <a name="compiler-error-c3116"></a>컴파일러 오류 C3116

'저장소 specifier': 인터페이스 메서드에 대 한 잘못 된 저장소 클래스

사용한 `typedef`, `register`, 또는 `static` 인터페이스 메서드에 대 한 저장소 클래스입니다. 저장소 클래스가 인터페이스 멤버에서 허용 되지 않습니다.

다음 샘플에서는 C3116 오류가 생성 됩니다.

```
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```