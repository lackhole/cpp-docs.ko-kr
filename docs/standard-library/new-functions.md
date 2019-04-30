---
title: '&lt;new&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: b5803b5fdf44392b6096f9c9a5ebdde7f94eae59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223734"
---
# <a name="ltnewgt-functions"></a>&lt;new&gt; 함수

|||
|-|-|
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|

## <a name="nothrow"></a>  nothrow

에 대 한 인수로 사용할 개체를 제공 합니다 **nothrow** 버전의 **새** 하 고 **삭제**합니다.

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>설명

이 개체는 매개 변수 형식 [std::nothrow_t](../standard-library/nothrow-t-structure.md)의 일치를 확인하기 위한 함수 인수로 사용됩니다.

### <a name="example"></a>예제

`std::nothrow_t`를 함수 매개 변수로 사용하는 방법의 예제는 [operator new](../standard-library/new-operators.md#op_new) 및 [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)를 참조하세요.

## <a name="set_new_handler"></a>  set_new_handler

될 때 호출 되는 사용자 함수를 설치 **new 연산자** 메모리 할당 시도에 실패 합니다.

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>매개 변수

*Pnew*<br/>
`new_handler` 를 설치 해야 합니다.

### <a name="return-value"></a>반환 값

첫 번째 호출의 경우 0이고 후속 호출의 경우 이전 `new_handler`입니다.

### <a name="remarks"></a>설명

함수 저장소 *Pnew* 정적에서 [새 처리기](../standard-library/new-typedefs.md#new_handler) 유지 관리 하는 포인터에는 다음 포인터에서 이전에 저장 된 값을 반환 합니다. 새 처리기를 사용해 [new 연산자](../standard-library/new-operators.md#op_new)(**size_t**).

### <a name="example"></a>예제

```cpp
// new_set_new_handler.cpp
// compile with: /EHsc
#include<new>
#include<iostream>

using namespace std;
void __cdecl newhandler( )
{
   cout << "The new_handler is called:" << endl;
   throw bad_alloc( );
   return;
}

int main( )
{
   set_new_handler (newhandler);
   try
   {
      while ( 1 )
      {
         new int[5000000];
         cout << "Allocating 5000000 ints." << endl;
      }
   }
   catch ( exception e )
   {
      cout << e.what( ) << endl;
   }
}
```

```Output
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
The new_handler is called:
bad allocation
```

## <a name="see-also"></a>참고자료

[\<new>](../standard-library/new.md)<br/>
