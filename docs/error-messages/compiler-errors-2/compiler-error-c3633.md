---
title: 컴파일러 오류 C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: 2d96a0e4f5f0b34c76f41058316c7f158f1a939d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385708"
---
# <a name="compiler-error-c3633"></a>컴파일러 오류 C3633

'member' 관리 되는 'type'의 멤버로 정의할 수 없습니다.

CLR 참조 클래스 데이터 멤버는 비 POD 수 없습니다 C++ 형식입니다.  POD의 네이티브 형식 CLR 형식에만 인스턴스화할 수 있습니다.  예를 들어, POD 형식이 복사 생성자 또는 대입 연산자를 포함할 수 없습니다.

## <a name="example"></a>예제

다음 샘플 C3633를 생성합니다.

```
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
