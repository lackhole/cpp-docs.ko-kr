---
title: 컴파일러 오류 C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: 3a0fd9c49a71f6f53d1a109378e3a6894bb68723
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175430"
---
# <a name="compiler-error-c2146"></a>컴파일러 오류 C2146

구문 오류: 'identifier' 식별자 앞 ' token' 누락

예상 컴파일러 `token` 거쳐 `identifier` 대신 합니다.  가능한 원인:

1. 맞춤법 또는 대/소문자 오류가 발생 했습니다.

1. 식별자의 선언에서 누락 된 형식 지정자입니다.

이 오류는 철자 오류로 인해 발생할 수 있습니다. 오류 [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) 일반적으로이 오류를 앞에 옵니다.

## <a name="example"></a>예제

다음 샘플 C2146를 생성합니다.

```
// C2146.cpp
class CDeclaredClass {};

class CMyClass {
   CUndeclared m_myClass;   // C2146
   CDeclaredClass m_myClass2;   // OK
};

int main() {
   int x;
   int t x;   // C2146 : missing semicolon before 'x'
}
```

## <a name="example"></a>예제

이 오류는 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 누락 된 `typename` 키워드입니다.

다음 샘플 Visual Studio.NET 2002에서는 컴파일되지만 Visual Studio.NET 2003에서는 실패 합니다.

```
// C2146b.cpp
// compile with: /c
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};

template <typename T>
X<T>::Y func() { }   // C2146

// OK
template <typename T>
typename X<T>::Y func() { }
```

## <a name="example"></a>예제

Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로이 오류가 나타납니다: 명시적 특수화가 더 이상 기본 템플릿에서 템플릿 매개 변수를 찾습니다.

사용 `T` 기본 템플릿에서에서 허용 되지 않는 명시적 특수화입니다. 시각적 개체의 Visual Studio.NET 2003 및 VISUAL Studio 버전에서 유효한 것으로 코드에 대 한 C++를 명시적으로 특수화 된 형식으로 모든 인스턴스의 특수화에 템플릿 매개 변수를 대체 합니다.

다음 샘플 Visual Studio.NET에서는 컴파일되지만 Visual Studio.NET 2003에서는 실패 합니다.

```
// C2146_c.cpp
// compile with: /c
template <class T>
struct S;

template <>
struct S<int> {
   T m_t;   // C2146
   int m_t2;   // OK
};
```