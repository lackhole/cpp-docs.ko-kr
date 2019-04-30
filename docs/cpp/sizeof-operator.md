---
title: sizeof 연산자
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: 9edd6420193fbc1ff6013c545b294851ce105848
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267221"
---
# <a name="sizeof-operator"></a>sizeof 연산자

형식의 크기에 따라 피연산자의 크기를 생성 **char**합니다.

> [!NOTE]
>  에 대 한 자세한 합니다 `sizeof ...` 연산자를 참조 하세요 [Ellipses 및 Variadic 템플릿](../cpp/ellipses-and-variadic-templates.md)합니다.

## <a name="syntax"></a>구문

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>설명

결과 **sizeof** 연산자는 유형이 `size_t`, 포함 파일에 정의 된 정수 계열 형식 \<stddef.h >. 이 연산자를 사용하면 프로그램에서 컴퓨터 종속 데이터 크기를 지정하지 않아도 됩니다.

피연산자 **sizeof** 다음 중 하나일 수 있습니다.

- 형식 이름. 사용 하도록 **sizeof** 형식 이름을 사용 하 여 이름을 괄호로 묶어야 합니다.

- 식입니다. 식과 함께 사용할 **sizeof** 괄호 없이 지정할 수 있습니다. 식은 계산되지 않습니다.

경우는 **sizeof** 형식의 개체에 연산자가 적용 **char**, 1 생성 합니다. 경우는 **sizeof** 연산자 배열에 적용 되 면 배열 식별자가 나타내는 포인터의 크기가 아닌 해당 배열의 바이트의 총 수를 생성 합니다. 배열 식별자가 나타내는 포인터의 크기를 가져오려면 전달할 매개 변수로 사용 하는 함수의 **sizeof**합니다. 예를 들어:

## <a name="example"></a>예제

```cpp
#include <iostream>
using namespace std;

size_t getPtrSize( char *ptr )
{
   return sizeof( ptr );
}

int main()
{
   char szHello[] = "Hello, world!";

   cout  << "The size of a char is: "
         << sizeof( char )
         << "\nThe length of " << szHello << " is: "
         << sizeof szHello
         << "\nThe size of the pointer is "
         << getPtrSize( szHello ) << endl;
}
```

## <a name="sample-output"></a>샘플 출력

```Output
The size of a char is: 1
The length of Hello, world! is: 14
The size of the pointer is 4
```

경우는 **sizeof** 연산자에 적용 됩니다는 **클래스**를 **구조체**, 또는 **union** 결과 형식이 있는 개체에 바이트 수 또한 추가 단어 경계에서 멤버를 맞추기 위해 안쪽 여백을 입력 합니다. 결과는 개별 멤버의 저장소 요구 사항을 추가하여 계산된 크기와 일치하지 않을 수도 있습니다. 합니다 [/Zp](../build/reference/zp-struct-member-alignment.md) 컴파일러 옵션 및 [팩](../preprocessor/pack.md) pragma 멤버에 대 한 맞춤 경계에 영향을 줍니다.

합니다 **sizeof** 연산자는 빈 클래스에 대해서도 0, 결과로 생성 하지 않습니다.

합니다 **sizeof** 다음 피연산자와 연산자를 사용할 수 없습니다.

- 함수 그러나 ( **sizeof** 함수에 대 한 포인터에 적용할 수 있습니다.)

- 비트 필드

- 정의되지 않은 클래스

- 형식 **void**합니다.

- 동적으로 할당된 배열

- 외부 배열

- 불완전한 형식

- 괄호로 묶인 불완전한 형식의 이름

경우는 **sizeof** 연산자 참조에 적용 되 면 결과 동일 처럼 **sizeof** 개체 자체에 적용 되었습니다.

크기가 지정 되지 않은 배열이 구조체의 마지막 요소를 **sizeof** 연산자는 배열 없는 구조체의 크기를 반환 합니다.

합니다 **sizeof** 연산자는 종종 형식의 식을 사용 하 여 배열의 요소 수를 계산 하는 데 사용 됩니다.

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>참고자료

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)