---
title: 사용자 정의 연산자(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
ms.openlocfilehash: cf80eb4c440c1308e8ea06a563c18569e4e4ddf2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774570"
---
# <a name="user-defined-operators-ccli"></a>사용자 정의 연산자(C++/CLI)

관리 되는 형식에 대 한 사용자 정의 연산자는 정적 멤버 또는 인스턴스 멤버 또는 전역 범위에서 허용 됩니다. 그러나 정적 연산자만 Visual 이외의 언어로 작성 된 클라이언트에 메타 데이터를 통해 액세스할 수는 C++입니다.

참조 형식 정적 사용자 정의 연산자의 매개 변수 중 하나 중 이어야 합니다.

- 핸들 (`type` ^) 바깥쪽 형식의 인스턴스로.

- 참조 형식 간접 (`type`^ & 또는 형식 ^ %) 포함 하는 형식 인스턴스 핸들입니다.

값 형식 정적 사용자 정의 연산자의 매개 변수 중 하나 중 이어야 합니다.

- 바깥쪽 값 형식과 동일한 형식입니다.

- 포인터 형식 간접 참조 (`type`^)를 포함 하는 형식입니다.

- 참조 형식 간접 참조 (`type`% 또는 `type`&)를 바깥쪽 형식입니다.

- 참조 형식 간접 참조 (`type`^ % 또는 `type`^ &) 핸들입니다.

다음 연산자를 정의할 수 있습니다.

|연산자|단항/이항 Forms?|
|--------------|--------------------------|
|!|단항|
|!=|이항|
|%|이항|
|&|단항 및 이항|
|&&|이항|
|*|단항 및 이항|
|+|단항 및 이항|
|++|단항|
|,|이항|
|-|단항 및 이항|
|--|단항|
|->|단항|
|/|이항|
|<|이항|
|<<|이항|
|\<=|이항|
|=|이항|
|==|이항|
|>|이항|
|>=|이항|
|>>|이항|
|^|이항|
|False|단항|
|true|단항|
|&#124;|이항|
|&#124;&#124;|이항|
|~|단항|

## <a name="example"></a>예제

```cpp
// mcppv2_user-defined_operators.cpp
// compile with: /clr
using namespace System;
public ref struct X {
   X(int i) : m_i(i) {}
   X() {}

   int m_i;

   // static, binary, user-defined operator
   static X ^ operator + (X^ me, int i) {
      return (gcnew X(me -> m_i + i));
   }

   // instance, binary, user-defined operator
   X^ operator -( int i ) {
      return gcnew X(this->m_i - i);
   }

   // instance, unary, user-defined pre-increment operator
   X^ operator ++() {
      return gcnew X(this->m_i++);
   }

   // instance, unary, user-defined post-increment operator
   X^ operator ++(int i) {
      return gcnew X(this->m_i++);
   }

   // static, unary user-defined pre- and post-increment operator
   static X^ operator-- (X^ me) {
      return (gcnew X(me -> m_i - 1));
   }
};

int main() {
   X ^hX = gcnew X(-5);
   System::Console::WriteLine(hX -> m_i);

   hX = hX + 1;
   System::Console::WriteLine(hX -> m_i);

   hX = hX - (-1);
   System::Console::WriteLine(hX -> m_i);

   ++hX;
   System::Console::WriteLine(hX -> m_i);

   hX++;
   System::Console::WriteLine(hX -> m_i);

   hX--;
   System::Console::WriteLine(hX -> m_i);

   --hX;
   System::Console::WriteLine(hX -> m_i);
}
```

```Output
-5
-4
-3
-2
-1
-2
-3
```

## <a name="example"></a>예제

다음 샘플을 사용 하는 경우 에서만 사용할 수 있는 연산자 합성 **/clr** 컴파일할 수 있습니다. 연산자를 통합에는 경우 정의 되지 않은, 대입 연산자의 왼쪽에는 CLR 형식에 할당 형식의 이항 연산자를 만듭니다.

```cpp
// mcppv2_user-defined_operators_2.cpp
// compile with: /clr
ref struct A {
   A(int n) : m_n(n) {};
   static A^ operator + (A^ r1, A^ r2) {
      return gcnew A( r1->m_n + r2->m_n);
   };
   int m_n;
};

int main() {
   A^ a1 = gcnew A(10);
   A^ a2 = gcnew A(20);

   a1 += a2;   // a1 = a1 + a2   += not defined in source
   System::Console::WriteLine(a1->m_n);
}
```

```Output
30
```

## <a name="see-also"></a>참고자료

[클래스 및 구조체(C++)](../extensions/classes-and-structs-cpp-component-extensions.md)
