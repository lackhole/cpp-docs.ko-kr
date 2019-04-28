---
title: nothrow_t 구조체
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: 2313c436a1fd25149fa7ea72f122a6f323b40028
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223625"
---
# <a name="nothrowt-structure"></a>nothrow_t 구조체

이 구조체는 함수가 예외를 발생시키는 대신 null 포인터를 반환하여 할당 오류를 보고해야 함을 나타내기 위해 new 연산자에 대한 함수 매개 변수로 사용됩니다.

## <a name="syntax"></a>구문

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>설명

컴파일러는 이 구조체를 통해 올바른 생성자 버전을 선택할 수 있습니다. [nothrow](../standard-library/new-functions.md#nothrow)는 `std::nothrow_t` 형식의 개체와 동일한 의미입니다.

## <a name="example"></a>예제

`std::nothrow_t`를 함수 매개 변수로 사용하는 방법의 예제는 [operator new](../standard-library/new-operators.md#op_new) 및 [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<new>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
