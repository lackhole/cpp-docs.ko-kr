---
title: 컴파일러 오류 C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 5be4836332f67f2064f60a3b058db159a18ca1e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160889"
---
# <a name="compiler-error-c2993"></a>컴파일러 오류 C2993

'identifier': 비형식 템플릿 매개 변수 'parameter' 형식이 잘못 되었습니다.

구조체 또는 공용 구조체 인수를 사용 하 여 템플릿을 선언할 수 없습니다. 구조체 및 공용 구조체를 템플릿 매개 변수로 전달 하려면 포인터를 사용 합니다.

다음 샘플에서는 C2993 오류가 생성 됩니다.

```
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

이 오류는 Visual Studio.NET 2003에서 수행 된 컴파일러 규칙 작업의 결과로 생성 됩니다: 부동 소수점 비형식 템플릿 매개 변수를 더 이상 허용 합니다. C++ 표준 부동 소수점 비형식 템플릿 매개 변수 허용 하지 않습니다.

부동을 전달할 함수 인수를 사용 하 여 지점 비형식 템플릿 매개 변수 함수 템플릿으로 인 경우 (이 코드를 시각적 개체의 Visual Studio.NET 2003 및 VISUAL Studio 버전에서 사용할 수 C++). 쉬운 해결 방법은 없습니다 있는지 클래스 템플릿입니다.

```
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```