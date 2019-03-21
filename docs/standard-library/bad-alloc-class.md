---
title: bad_alloc 클래스
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 63b474d0209a5cc385de9dc11b56d5de8382a9cf
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751533"
---
# <a name="badalloc-class"></a>bad_alloc 클래스

이 클래스는 할당 요청이 성공하지 못했음을 나타내기 위해 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class bad_alloc : public exception {
    bad_alloc();
virtual ~bad_alloc();

};
```

## <a name="remarks"></a>설명

반환한 값 `what` 은 구현 시 정의 된 C 문자열입니다. 멤버 함수는 예외를 발생시키지 않습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<new>

**네임스페이스:** std

## <a name="example"></a>예제

```cpp
// bad_alloc.cpp
// compile with: /EHsc
#include<new>
#include<iostream>
using namespace std;

int main() {
   char* ptr;
   try {
      ptr = new char[(~unsigned int((int)0)/2) - 1];
      delete[] ptr;
   }
   catch( bad_alloc &ba) {
      cout << ba.what( ) << endl;
   }
}
```

## <a name="sample-output"></a>샘플 출력

```Output
bad allocation
```

## <a name="requirements"></a>요구 사항

**헤더:** \<new>

## <a name="see-also"></a>참고자료

[exception 클래스](../standard-library/exception-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
