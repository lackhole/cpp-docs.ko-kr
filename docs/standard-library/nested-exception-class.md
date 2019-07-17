---
title: nested_exception 클래스
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: a568a8d9a3817883656406d63c3dd948539bb385
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268525"
---
# <a name="nestedexception-class"></a>nested_exception 클래스

클래스는 다중 상속 사용에 대 한 예외를 설명합니다. 현재 처리 된 예외를 캡처하고 저장 한 다음 나중에 사용 합니다.

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
|[rethrow_nested](#rethrow_nested)|저장 된 예외를 throw합니다.|
|[nested_ptr](#nested_ptr)|저장 된 예외를 반환합니다.|

### <a name="op_as"></a> 연산자 =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>반환 값

이 캡처 저장된 예외 `nested_exception` 개체입니다.

### <a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>설명

하는 경우 `nested_ptr()` 함수를 호출 하 여 null 포인터를 반환 `std::terminate()`합니다. 에 의해 캡처된 저장된 예외를 throw 하는 고, 그렇지 `*this`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<exception>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[exception 클래스](../standard-library/exception-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
