---
title: nested_exception 클래스
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 5741b3aa255f915500f5fe79ab5374c8c86f8814
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460187"
---
# <a name="nestedexception-class"></a>nested_exception 클래스

이 클래스는 여러 상속을 사용 하는 예외를 설명 합니다. 현재 처리 된 예외를 캡처하여 나중에 사용할 수 있도록 저장 합니다.

## <a name="syntax"></a>구문

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[operator=](#op_as)||

### <a name="functions"></a>함수

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|저장 된 예외를 throw 합니다.|
|[nested_ptr](#nested_ptr)|저장 된 예외를 반환 합니다.|

### <a name="op_as"></a>연산자 =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>반환 값

이 `nested_exception` 개체가 캡처한 저장 된 예외입니다.

### <a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>설명

가 `nested_ptr()` null 포인터를 반환 하면 함수는를 `std::terminate()`호출 합니다. 그렇지 않으면에서 `*this`캡처한 저장 된 예외를 throw 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<exception>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[exception 클래스](../standard-library/exception-class.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
