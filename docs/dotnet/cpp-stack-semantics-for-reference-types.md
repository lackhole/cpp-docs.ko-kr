---
title: 참조 형식에 대한 C++ 스택 의미 체계
ms.date: 11/04/2016
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
ms.openlocfilehash: 69771de120dc413496a3b7b0613e51a13d208e22
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772607"
---
# <a name="c-stack-semantics-for-reference-types"></a>참조 형식에 대한 C++ 스택 의미 체계

Visual 하기 전에 C++ 2005 참조 형식의 인스턴스를 만들 수 있었습니다를 사용 하는 `new` 가비지에 개체를 생성 하는 연산자가 수집 되는 힙에 합니다. 그러나 스택에 네이티브 형식의 인스턴스를 만드는 데 사용할 수 있는 동일한 구문을 사용 하는 참조 형식의 인스턴스로 만들 수 있습니다. 따라서 사용 하 여 필요가 없습니다 [ref new, gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) 참조 형식의 개체를 만듭니다. 및 개체 범위를 벗어나면 컴파일러가 개체의 소멸자를 호출 합니다.

## <a name="remarks"></a>설명

컴파일러 내부적으로 가비지 수집 힙에서 인스턴스를 만들어지지는 스택 의미 체계를 사용 하 여 참조 형식의 인스턴스를 만들면 (사용 하 여 `gcnew`).

함수 시그니처 또는 반환 형식 값으로 참조 형식의 인스턴스를 포함 하는 경우 함수는 (modreq)와 특별 한 처리가 필요 하다는 메타 데이터에 표시 됩니다. 이 특수 처리는 현재 시각적 개체에만 제공한 C++ 클라이언트 스택 의미 체계를 사용 하 여 만든 참조 형식을 사용 하는 데이터 또는 함수를 사용 중인 다른 언어는 현재 지원 하지 않습니다.

사용 하는 하나의 이유 `gcnew` (동적 할당) 형식에 소멸자가 되지 않은 경우 의미 체계는 되어야 하는 스택 대신 합니다. 또한 함수 시그니처에서 스택 의미 체계를 사용 하 여 만든 참조 형식을 사용 하는 것은 불가능 함수 Visual 이외의 언어에서 사용할 수 있도록 하려는 경우 C++입니다.

컴파일러는 참조 형식에 대 한 복사 생성자를 생성 하지 않습니다. 따라서 시그니처에서 값에서 참조 형식을 사용 하는 함수를 정의 하는 경우 참조 형식에 대 한 복사 생성자를 정의 해야 합니다. 참조 형식에 대 한 복사 생성자에 다음 형태의 서명이: `R(R%){}`합니다.

컴파일러는 참조 형식에 대 한 기본 대입 연산자를 생성 하지 않습니다. 대입 연산자를 사용 하면 스택 의미 체계를 사용 하 여 개체를 만들고 스택 의미 체계를 사용 하 여 만든 기존 개체를 사용 하 여 초기화할 수 있습니다. 대입 연산자는 참조 형식에 대 한 다음과 같은 형식의 시그니처가: `void operator=( R% ){}`합니다.

스택 의미 체계를 사용 하 여 참조 형식에 대 한 중요 한 리소스를 해제 하는 형식의 소멸자를 명시적으로 소멸자를 호출 필요가 없습니다 (호출 또는 `delete`). 참조 형식에서 소멸자에 대 한 자세한 내용은 참조 하세요. [소멸자 및 종료자 방법에서: 클래스 및 구조체 정의 및 사용 (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.

컴파일러에서 생성 된 할당 연산자를 일반적인 표준에 따라는 C++ 다음 항목이 추가 된 규칙:

- 모든 비정적 데이터 멤버는 참조 형식에 대 한 핸들 형식의 됩니다 단순 복사 (포인터가 형식의 비정적 데이터 멤버 처럼 처리 됨).

- 값 형식을 단순 됩니다는 형식의 모든 비정적 데이터 멤버 복사 합니다.

- 형식이 참조 형식의 인스턴스는 모든 비정적 데이터 멤버는 참조 형식 복사 생성자에 대 한 호출을 호출 합니다.

컴파일러에서는 `%` 기본 핸들 형식으로 스택 의미 체계를 사용 하 여 만든 참조 형식의 인스턴스를 변환할 단항 연산자입니다.

참조 형식은 스택 의미 체계를 사용 하 여 사용 하기 위해 사용할 수 있습니다.

- [delegate(C++ 구성 요소 확장)](../extensions/delegate-cpp-component-extensions.md)

- [배열](../extensions/arrays-cpp-component-extensions.md)

- <xref:System.String>

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 코드 샘플에서는 스택 의미 체계를 사용 하 여 참조 형식 인스턴스를 선언 하는 방법을 보여 줍니다. 방법을 대입 연산자 및 복사 생성자의 작동 및 스택 의미 체계를 사용 하 여 만든 참조 형식을 사용 하 여 추적 참조를 초기화 하는 방법입니다.

### <a name="code"></a>코드

```cpp
// stack_semantics_for_reference_types.cpp
// compile with: /clr
ref class R {
public:
   int i;
   R(){}

   // assignment operator
   void operator=(R% r) {
      i = r.i;
   }

   // copy constructor
   R(R% r) : i(r.i) {}
};

void Test(R r) {}   // requires copy constructor

int main() {
   R r1;
   r1.i = 98;

   R r2(r1);   // requires copy constructor
   System::Console::WriteLine(r1.i);
   System::Console::WriteLine(r2.i);

   // use % unary operator to convert instance using stack semantics
   // to its underlying handle
   R ^ r3 = %r1;
   System::Console::WriteLine(r3->i);

   Test(r1);

   R r4;
   R r5;
   r5.i = 13;
   r4 = r5;   // requires a user-defined assignment operator
   System::Console::WriteLine(r4.i);

   // initialize tracking reference
   R % r6 = r4;
   System::Console::WriteLine(r6.i);
}
```

### <a name="output"></a>출력

```Output
98
98
98
13
13
```

## <a name="see-also"></a>참고자료

[클래스 및 구조체(C++)](../extensions/classes-and-structs-cpp-component-extensions.md)
