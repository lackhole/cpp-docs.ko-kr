---
title: '&lt;system_error&gt; 함수'
ms.date: 03/15/2019
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 78be83af678b553babbf1cde3d96c1507940b611
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412113"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; 함수

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|||

## <a name="generic_category"></a> generic_category

일반 오류의 범주를 나타냅니다.

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>설명

합니다 `generic_category` 개체의 구현인 [error_category](../standard-library/error-category-class.md)합니다.

## <a name="make_error_code"></a>  make_error_code

오류 코드 개체를 만듭니다.

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>매개 변수

*error*\
`std::errc` 오류 코드 개체에 저장할 열거형 값입니다.

### <a name="return-value"></a>반환 값

오류 코드 개체입니다.

### <a name="remarks"></a>설명

## <a name="make_error_condition"></a>  make_error_condition

오류 조건 개체를 만듭니다.

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>매개 변수

*error*\
`std::errc` 오류 코드 개체에 저장할 열거형 값입니다.

### <a name="return-value"></a>반환 값

오류 조건 개체입니다.

### <a name="remarks"></a>설명

## <a name="system_category"></a>  system_category

하위 수준 시스템 오버플로로 인해 발생하는 오류의 범주를 나타냅니다.

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>설명

합니다 `system_category` 개체의 구현인 [error_category](../standard-library/error-category-class.md)합니다.

## <a name="see-also"></a>참고자료

[\<system_error>](../standard-library/system-error.md)<br/>
