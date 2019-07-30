---
title: is_error_code_enum 클래스
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 4080c62034b224a9553eca2787aa1c2f2cf69ab8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454621"
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

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
