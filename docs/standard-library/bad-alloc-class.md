---
title: bad_alloc 클래스
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 9d1d81e393b4a3eb27ea08bc53634bfcbc119240
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243973"
---
# <a name="badalloc-class"></a>bad_alloc 클래스

이 클래스는 할당 요청이 성공하지 못했음을 나타내기 위해 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class bad_alloc : public exception {
    bad_alloc();
    virtual ~bad_alloc();
    bad_alloc(const bad_alloc&);
    bad_alloc& operator=(const bad_alloc&);
    const char* what() const override;
};
```

## <a name="remarks"></a>설명

반환한 값 `what` 은 구현 시 정의 된 C 문자열입니다. 멤버 함수는 예외를 발생시키지 않습니다.

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

```Output
bad allocation
```
