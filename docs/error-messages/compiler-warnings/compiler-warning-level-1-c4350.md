---
title: 컴파일러 경고(수준 1) C4350
ms.date: 11/04/2016
f1_keywords:
- C4350
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
ms.openlocfilehash: 8f23751151d8d83c68608d926ef422d56dde41a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384207"
---
# <a name="compiler-warning-level-1-c4350"></a>컴파일러 경고(수준 1) C4350

동작 변경: 'member1'이(가) 'member2' 대신 호출됩니다.

비 const 참조는 rvalue는 바인딩할 수 없습니다. 시각적 개체의 버전에서 C++ Visual Studio 2003 하기 전에 직접 초기화의 비 const 참조는 rvalue를 바인딩할 수 있었습니다. 이 코드는 이제 경고를 제공합니다.

이전 버전과 호환성을 비 const 참조에 대 한 rvalue를 바인딩할 수 있지만 표준 변환은 기본 가능 합니다.

이 경고 시각적 개체에서 변경 된 동작을 나타내는 C++ .NET 2002 컴파일러. 사용 하도록 설정 하는 경우이 경고 올바른 코드에 대 한 가능한 주어질 수 있습니다. 예를 들어, 해당 주어질 수 있습니다 사용 하는 경우는 **auto_ptr** 클래스 템플릿.

이 경고를 받게 되 면 rvalue 비 const 참조를 사용 하는 경우를 확인 하기 위해 코드를 검사 합니다. Const 참조를 추가 하거나 추가 const 참조 오버 로드를 제공 하는 문제를 해결할 수 있습니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

다음 샘플에서는 C4350 오류가 생성 됩니다.

```cpp
// C4350.cpp
// compile with: /W1
#pragma warning (default : 4350)
class A {};

class B
{
public:
   B(B&){}
   // try the following instead:
   // B(const B&){}

   B(A){}
   operator A(){ return A();}
};

B source() { return A(); }

int main()
{
   B ap(source());   // C4350
}
```