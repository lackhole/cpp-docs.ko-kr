---
title: default_delete 구조체
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: e9e1fcc68539e55486f4ea27e6dd5c49bed11fdf
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269265"
---
# <a name="defaultdelete-struct"></a>default_delete 구조체

나누기 연산을 수행 하는 미리 정의 된 함수 개체 (`operator/`) 인수에 대해 합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>요구 사항

**헤더:** \<memory>

**네임스페이스:** std

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[default_delete](#default_delete)|`default_delete` 형식의 개체에 대한 생성자입니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator()](#op_paren)|액세스 하는 참조 연산자 `default_delete`합니다.|

## <a name="default_delete"></a> default_delete

`default_delete` 형식의 개체에 대한 생성자입니다.

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="op_paren"></a> operator()

액세스 하는 참조 연산자 `default_delete`합니다.

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>참고자료

[\<memory>](../standard-library/memory.md)
