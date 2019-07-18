---
title: error_category 클래스
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
ms.openlocfilehash: 308fa1a2309ddfda1a02fe6a687360185c1e7c6e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245847"
---
# <a name="errorcategory-class"></a>error_category 클래스

오류 코드 범주를 설명하는 개체에 대한 추상, 공통 기본을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class error_category;

constexpr error_category() noexcept;
virtual ~error_category();
error_category(const error_category&) = delete
```

## <a name="remarks"></a>설명

미리 정의된 두 개의 [generic_category](../standard-library/system-error-functions.md#generic_category) 및 [system_category](../standard-library/system-error-functions.md#system_category) 개체가 `error_category`를 구현합니다.

## <a name="members"></a>멤버

### <a name="typedefs"></a>형식 정의

|||
|-|-|
|[value_type](#value_type)|저장된 오류 코드 값을 나타내는 형식입니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[default_error_condition](#default_error_condition)|오류 조건 개체에 대한 오류 코드 값을 저장합니다.|
|[equivalent](#equivalent)|오류 개체가 동일한지 여부를 지정하는 값을 반환합니다.|
|[generic_category](#generic)||
|[message](#message)|지정된 오류 코드의 이름을 반환합니다.|
|[name](#name)|범주 이름을 반환합니다.|
|[system_category](#system)||

### <a name="operators"></a>연산자

|||
|-|-|
|[operator=](#op_as)||
|[연산자==](#op_eq_eq)|`error_category` 개체가 같은지 테스트합니다.|
|[operator!=](#op_neq)|`error_category` 개체가 같지 않은지 테스트합니다.|
|[operator<](#op_lt)|[error_category](../standard-library/error-category-class.md) 개체가 비교를 위해 전달된 `error_category` 개체보다 작은지 테스트합니다.|

## <a name="default_error_condition"></a> default_error_condition

오류 조건 개체에 대한 오류 코드 값을 저장합니다.

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>매개 변수

*_Errval*\
[error_condition](../standard-library/error-condition-class.md)에 저장할 오류 코드 값입니다.

### <a name="return-value"></a>반환 값

`error_condition(_Errval, *this)`를 반환합니다.

### <a name="remarks"></a>설명

### <a name="equivalent"></a> 해당

오류 개체가 동일한지 여부를 지정하는 값을 반환합니다.

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

#### <a name="parameters"></a>매개 변수

*_Errval*\
비교할 오류 코드 값입니다.

*_Cond*\
비교할 [error_condition](../standard-library/error-condition-class.md) 개체입니다.

*(_C)* \
비교할 [error_code](../standard-library/error-code-class.md) 개체입니다.

#### <a name="return-value"></a>반환 값

**true 이면** 범주 및 값 같으면이 고, 그렇지 않으면 **false**합니다.

#### <a name="remarks"></a>설명

첫 번째 멤버 함수는 `*this == _Cond.category() && _Cond.value() == _Errval`을 반환합니다.

두 번째 구성원 함수는 `*this == _Code.category() && _Code.value() == _Errval`를 반환합니다.

### <a name="generic"></a> generic_category

```cpp
const error_category& generic_category();
```

### <a name="message"></a> 메시지

지정된 오류 코드의 이름을 반환합니다.

```cpp
virtual string message(error_code::value_type val) const = 0;
```

#### <a name="parameters"></a>매개 변수

*val*\
설명할 오류 코드 값입니다.

#### <a name="return-value"></a>반환 값

오류 코드의 설명이 포함 된 이름을 반환 *val* 범주에 대 한 합니다.

#### <a name="remarks"></a>설명

### <a name="name"></a> 이름

범주 이름을 반환합니다.

```cpp
virtual const char *name() const = 0;
```

#### <a name="return-value"></a>반환 값

범주 이름을 null 종료 바이트 문자열로 반환합니다.

### <a name="op_as"></a> 연산자 =

```cpp
error_category& operator=(const error_category&) = delete;
```


### <a name="op_eq_eq"></a> 연산자 = =

`error_category` 개체가 같은지 테스트합니다.

```cpp
bool operator==(const error_category& right) const;
```

#### <a name="parameters"></a>매개 변수

*오른쪽*\
같은지 테스트할 개체입니다.

#### <a name="return-value"></a>반환 값

개체가 같으면 **true**이고, 개체가 같지 않으면 **false**입니다.

#### <a name="remarks"></a>설명

이 구성원 연산자는 `this == &right`를 반환합니다.

### <a name="op_neq"></a> operator!=

`error_category` 개체가 같지 않은지 테스트합니다.

```cpp
bool operator!=(const error_category& right) const;
```

#### <a name="parameters"></a>매개 변수

*오른쪽*\
같지 않은지 테스트할 개체입니다.

#### <a name="return-value"></a>반환 값

**true** 경우는 `error_category` 개체와 같지 않습니다. 합니다 `error_category` 개체가 전달 *오른쪽*이 고 그렇지 않으면 **false**합니다.

#### <a name="remarks"></a>설명

멤버 연산자는 `(!*this == right)`을 반환합니다.

### <a name="op_lt"></a> 연산자&lt;

[error_category](../standard-library/error-category-class.md) 개체가 비교를 위해 전달된 `error_category` 개체보다 작은지 테스트합니다.

```cpp
bool operator<(const error_category& right) const;
```

#### <a name="parameters"></a>매개 변수

*오른쪽*\
비교할 `error_category` 개체입니다.

#### <a name="return-value"></a>반환 값

`error_category` 개체가 비교를 위해 전달된 `error_category` 개체보다 작으면 **true**이고, 그렇지 않으면 **false**입니다.

#### <a name="remarks"></a>설명

멤버 연산자는 `this < &right`을 반환합니다.

### <a name="system"></a> system_category

```cpp
const error_category& system_category();
```

### <a name="value_type"></a> value_type

저장된 오류 코드 값을 나타내는 형식입니다.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>설명

이 형식 정의 대 한 동의어가 **int**합니다.
