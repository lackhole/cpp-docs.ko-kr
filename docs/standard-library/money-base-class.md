---
title: money_base 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 5b19635cf4d2cce58ec50226c463a075cfac5b0f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455570"
---
# <a name="moneybase-class"></a>money_base 클래스

이 클래스는 템플릿 클래스 [moneypunct](../standard-library/moneypunct-class.md)의 모든 특수화에 공통적인 열거형과 구조체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>설명

열거형 `part` 은 구조체 패턴의 배열 필드 요소에서 가능한 값을 설명 합니다. 의 `part` 값은 다음과 같습니다.

- `none`0 개 이상의 공백을 찾거나 아무것도 생성 하지 않습니다.

- `sign`양수 또는 음수 기호를 일치 또는 생성 합니다.

- `space`0 개 이상의 공백을 찾거나 공백을 생성 하려면입니다.

- `symbol`통화 기호를 일치 또는 생성 하려면입니다.

- `value`통화 값을 일치 하거나 생성 하려면입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
