---
title: 컴파일러 오류 C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 406b388460b3d449471c884dd6461f2ce59a10f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365717"
---
# <a name="compiler-error-c3269"></a>컴파일러 오류 C3269

'function': '...'를 사용 하 여 관리 되는 또는 WinRTtype 멤버 함수를 선언할 수 없습니다

관리되는 클래스 멤버 함수와 WinRT 클래스 멤버 함수는 변수 길이 매개 변수 목록을 선언할 수 없습니다.

다음 샘플에서는 C3269 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```
