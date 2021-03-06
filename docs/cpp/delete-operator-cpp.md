---
title: delete 연산자 (C++)
ms.date: 08/12/2019
f1_keywords:
- delete_cpp
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
ms.openlocfilehash: 3b00bf78d286ba530dee85240236a2a9ea171113
ms.sourcegitcommit: a146b169664c001406a0cccc7fbda1b8d7be5078
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2019
ms.locfileid: "69024637"
---
# <a name="delete-operator-c"></a>delete 연산자 (C++)

메모리 블록을 할당 취소합니다.

## <a name="syntax"></a>구문

> [`::`] `delete` *cast 식*\
> [`::`] `delete []` *cast 식*

## <a name="remarks"></a>설명

*Cast 식* 인수는 [new 연산자](../cpp/new-operator-cpp.md)를 사용 하 여 만든 개체에 대해 이전에 할당 된 메모리 블록에 대 한 포인터 여야 합니다. **Delete** 연산자는 **void** 형식의 결과를 가지 므로 값을 반환 하지 않습니다. 예를 들어:

```cpp
CDialog* MyDialog = new CDialog;
// use MyDialog
delete MyDialog;
```

**New** 와 함께 할당 되지 않은 개체에 대 한 포인터에 **delete** 를 사용 하면 예기치 않은 결과가 발생 합니다. 그러나 값이 0 인 포인터에 **delete** 를 사용할 수 있습니다. 이 프로 비전은 **new** 가 실패 시 0을 반환 하는 경우 실패 한 **새** 작업의 결과를 삭제 하는 것은 무해 함을 의미 합니다. 자세한 내용은 [new 및 Delete 연산자](../cpp/new-and-delete-operators.md)를 참조 하세요.

**New** 및 **delete** 연산자는 배열을 비롯 한 기본 제공 형식에도 사용할 수 있습니다. 에서 `pointer` 배열을 참조 하는 경우에는 `pointer`다음에`[]`빈 대괄호 ()를 추가 합니다.

```cpp
int* set = new int[100];
//use set[]
delete [] set;
```

개체에 **delete** 연산자를 사용 하면 해당 메모리가 할당 해제 됩니다. 개체가 삭제된 후에 포인터를 역참조하는 프로그램에서는 예기치 않은 결과나 충돌이 발생할 수 있습니다.

**Delete** 를 사용 하 여 C++ 클래스 개체의 메모리 할당을 취소 하는 경우 개체의 소멸자는 개체의 메모리 할당이 취소 되기 전에 호출 됩니다 (개체에 소멸자가 있는 경우).

**Delete** 연산자에 대 한 피연산자가 수정할 수 있는 l-value 이면 개체가 삭제 된 후 해당 값이 정의 되지 않습니다.

[/Sdl (추가 보안 검사 사용)](/cpp/build/reference/sdl-enable-additional-security-checks) 컴파일러 옵션을 지정 하는 경우 개체가 삭제 된 후 **delete** 연산자에 대 한 피연산자가 잘못 된 값으로 설정 됩니다.

## <a name="using-delete"></a>삭제 사용

[Delete 연산자](../cpp/delete-operator-cpp.md)에 대 한 두 가지 구문 변형이 있습니다. 하나는 단일 개체이 고 다른 하나는 개체의 배열입니다. 다음 코드 조각에서는 서로 어떻게 다른 지를 보여 줍니다.

```cpp
// expre_Using_delete.cpp
struct UDType
{
};

int main()
{
   // Allocate a user-defined object, UDObject, and an object
   //  of type double on the free store using the
   //  new operator.
   UDType *UDObject = new UDType;
   double *dObject = new double;
   // Delete the two objects.
   delete UDObject;
   delete dObject;
   // Allocate an array of user-defined objects on the
   // free store using the new operator.
   UDType (*UDArr)[7] = new UDType[5][7];
   // Use the array syntax to delete the array of objects.
   delete [] UDArr;
}
```

다음 두 가지 경우는 정의 되지 않은 결과를 생성 합니다. 즉,`delete []`개체에 delete () 배열을 사용 하 고, 배열에서 delete의 nonarray 형식을 사용 합니다.

## <a name="example"></a>예제

**Delete**사용에 대 한 예는 [new operator](../cpp/new-operator-cpp.md)를 참조 하세요.

## <a name="how-delete-works"></a>delete 작동 방식

Delete 연산자는 **operator delete**함수를 호출 합니다.

클래스 형식이 아닌 개체 ([클래스](../cpp/class-cpp.md), [구조체](../cpp/struct-cpp.md)또는 [공용 구조체](../cpp/unions.md))의 경우 전역 delete 연산자가 호출 됩니다. 클래스 형식의 개체에 대해 delete 식이 단항 범위 확인 연산자 (`::`)로 시작 하는 경우 할당 취소 함수의 이름이 전역 범위에서 확인 됩니다. 그렇지 않으면 delete 연산자가 메모리 할당을 해제하기 전에 개체에 대한 소멸자를 호출합니다(포인터가 null이 아닌 경우). delete 연산자는 클래스별로 정의될 수 있습니다. 지정된 클래스에 이러한 정의가 없는 경우 전역 delete 연산자가 호출됩니다. 삭제 식을 사용하여 정적 형식이 가상 소멸자인 클래스 개체를 할당 해제하는 경우, 할당 해제 함수는 개체의 동적 형식에 대한 가상 소멸자를 통해 확인됩니다.

## <a name="see-also"></a>참고자료

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)\
[키워드](../cpp/keywords-cpp.md)\
[new 및 delete 연산자](../cpp/new-and-delete-operators.md)