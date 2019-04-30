---
title: 컴파일러 경고(수준 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: e1b787e7149afe93fb50cc1e6ceaecba2e787876
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384256"
---
# <a name="compiler-warning-level-1-c4291"></a>컴파일러 경고(수준 1) C4291

'declaration': 찾을 수 없는 일치 하는 연산자 delete 초기화 예외를 throw 하는 경우 메모리 해제 되지 않습니다.

Placement [새](../../cpp/new-operator-cpp.md) 되에 없는 배치 [삭제](../../cpp/delete-operator-cpp.md)합니다.

연산자를 사용 하 여 개체에 대 한 메모리를 할당 하는 경우 **새**, 개체의 생성자가 호출 됩니다. 생성자는 예외를 throw 하는 경우 개체에 대해 할당 된 메모리를 할당 취소 합니다. 이렇게 하기 위해서는 운영자 **삭제할** 연산자와 일치 하는 함수가 존재 **새**합니다.

연산자를 사용 하는 경우 **새** 모든 추가 인수 및 사용 하 여 컴파일 없이 [/GX](../../build/reference/gx-enable-exception-handling.md)합니다 [/EHs](../../build/reference/eh-exception-handling-model.md), /EHa 컴파일러 예외 처리를 사용 하도록 설정 하는 옵션에 코드를 생성 합니다 또는 연산자를 호출 **삭제** 생성자에서 예외가 throw 됩니다.

배치 형식을 사용 하는 경우는 **새** 연산자 (폼 크기 인수를 사용 하 여 할당) 및 개체의 생성자가 예외를 throw 컴파일러 연산자를호출하는코드생성됩니다**삭제할**; 경우 연산자의 배치 형태만 실행 하면 있지만 **삭제할** 연산자의 배치 형태에 일치 하는 **새** 메모리를 할당 합니다. 예를 들어:

```
// C4291.cpp
// compile with: /EHsc /W1
#include <malloc.h>

class CList
{
public:
   CList(int)
   {
      throw "Fail!";
   }
};

void* operator new(size_t size, char* pszFilename, int nLine)
{
   return malloc(size);
}

int main(void)
{
   try
   {
      // This will call ::operator new(unsigned int) to allocate heap
      // memory. Heap memory pointed to by pList1 will automatically be
      // deallocated by a call to ::operator delete(void*) when
      // CList::CList(int) throws an exception.
      CList* pList1 = new CList(10);
   }
   catch (...)
   {
   }

   try
   {
      // This will call the overloaded ::operator new(size_t, char*, int)
      // to allocate heap memory. When CList::CList(int) throws an
      // exception, ::operator delete(void*, char*, int) should be called
      // to deallocate the memory pointed to by pList2. Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291
   }
   catch (...)
   {
   }
}
```

위의 예제 때문에 C4291 경고를 생성 연산자의 배치 형식이 없으므로 **삭제** 정의 된 연산자의 배치 형식을 일치 하는 **새**합니다. 문제를 해결 하기 위해 위에 다음 코드를 삽입할 **주**합니다. 모든 오버 로드 된 연산자 **삭제** 함수 매개 변수 오버 로드 된 연산자의 일치 **새**, 첫 번째 매개 변수를 제외 하 고 있습니다.

```
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```