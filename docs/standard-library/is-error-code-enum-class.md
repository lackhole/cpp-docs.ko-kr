---
title: is_error_code_enum 클래스
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: d890eb6a1b7c93f9ae5b87018c3bf1d6eeae8abb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336482"
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum 클래스

[error_code](../standard-library/error-code-class.md) 열거형을 테스트하는 형식 조건자를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <_Enum>
class is_error_code_enum;
```

## <a name="remarks"></a>설명

이 [형식 조건자](../standard-library/type-traits.md)의 인스턴스는 `_Enum` 형식이 `error_code` 형식의 개체에 저장하는 데 적합한 열거형 값이면 true입니다.

사용자 정의 형식의 경우 이 형식에 특수화를 추가할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<system_error>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
