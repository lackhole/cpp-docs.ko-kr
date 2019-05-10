---
title: delete 연산자 (C++)
ms.date: 11/04/2016
f1_keywords:
- delete_cpp
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
ms.openlocfilehash: 5e4f5685ea1bb8cd7c405373ba774fe36af08672
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398968"
---
# <a name="delete-operator-c"></a>delete 연산자 (C++)

메모리 블록을 할당 취소합니다.

## <a name="syntax"></a>구문

```
[::] delete cast-expression
[::] delete [ ] cast-expression
```

## <a name="remarks"></a>설명

*캐스트 식* 인수를 사용 하 여 만든 개체에 대해 이전에 할당 된 메모리 블록에 대 한 포인터 여야 합니다 [new 연산자](../cpp/new-operator-cpp.md)합니다. 합니다 **삭제** 연산자의 결과 유형이 **void** 및 값을 반환 하지 않습니다. 예를 들어:

```cpp
CDialog* MyDialog = new CDialog;
// use MyDialog
delete MyDialog;
```

사용 하 여 **삭제할** 사용 하 여 할당 되지 않은 개체에 대 한 포인터 **새** 예기치 않은 결과 제공 합니다. 그러나 사용할 수 있습니다 **삭제** 값이 0 인 포인터에 대 한 합니다. 이 프로 비전을 의미 하는 경우 **새** 실패 한 결과 삭제 하는 중 오류가 발생 하면 0을 반환 합니다. **새** 작업은 무시 해도 됩니다. 참조 [새 및 delete 연산자](../cpp/new-and-delete-operators.md) 자세한 내용은 합니다.

합니다 **새** 하 고 **삭제** 연산자 배열을 포함 하는 기본 제공 형식에 사용할 수도 있습니다. `pointer`가 배열을 가리키는 경우 `pointer` 앞에 빈 대괄호를 넣습니다.

```cpp
int* set = new int[100];
//use set[]
delete [] set;
```

사용 하는 **삭제** 개체에 연산자의 메모리 할당을 취소 합니다. 개체가 삭제된 후에 포인터를 역참조하는 프로그램에서는 예기치 않은 결과나 충돌이 발생할 수 있습니다.

때 **삭제할** 에 대 한 메모리 할당을 취소 하는 데 사용 되는 C++ 클래스 개체를 개체의 소멸자 (개체에 소멸자가) 하는 경우 개체의 메모리 할당이 취소 되기 전에 호출 됩니다.

경우에 있는 피연산자는 **삭제** 연산자는 수정 가능한 l-value 이면 개체가 삭제 된 후에 해당 값이 정의 되지 않습니다.

## <a name="using-delete"></a>삭제 사용

두 가지 구문 변형이 대 한 합니다 [delete 연산자](../cpp/delete-operator-cpp.md): 단일 개체 및 개체의 배열에 대 한 기타 하나입니다. 다음 코드에서는 두 가지 변형의 차이점을 보여 줍니다.

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

개체에 대해 delete의 배열 형태(delete [ ])를 사용하는 경우와 배열에 대해 delete의 비배열 형태를 사용하는 경우에는 정의되지 않은 결과가 생성됩니다.

## <a name="example"></a>예제

에 대 한 예제 **삭제**를 참조 하십시오 [new 연산자](../cpp/new-operator-cpp.md)합니다.

## <a name="how-delete-works"></a>delete 작동 방식

함수를 호출 하는 delete 연산자 **delete 연산자**합니다.

아닌 개체의 클래스 형식 ([클래스](../cpp/class-cpp.md)를 [구조체](../cpp/struct-cpp.md), 또는 [union](../cpp/unions.md)), 전역 delete 연산자가 호출 됩니다. 클래스 형식 개체의 경우에는 삭제 식이 단항 범위 확인 연산자(::)로 시작되면 할당 해제 함수의 이름이 전역 범위에서 확인됩니다. 그렇지 않으면 delete 연산자가 메모리 할당을 해제하기 전에 개체에 대한 소멸자를 호출합니다(포인터가 null이 아닌 경우). delete 연산자는 클래스별로 정의될 수 있습니다. 지정된 클래스에 이러한 정의가 없는 경우 전역 delete 연산자가 호출됩니다. 삭제 식을 사용하여 정적 형식이 가상 소멸자인 클래스 개체를 할당 해제하는 경우, 할당 해제 함수는 개체의 동적 형식에 대한 가상 소멸자를 통해 확인됩니다.

## <a name="see-also"></a>참고자료

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[new 및 delete 연산자](../cpp/new-and-delete-operators.md)