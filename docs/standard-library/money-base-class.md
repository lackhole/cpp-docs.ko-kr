---
title: money_base 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: c614832b0cbb1cc23e42ecb3a939ccf1334a5cea
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689319"
---
# <a name="money_base-class"></a>money_base 클래스

이 클래스는 클래스 템플릿 [moneypunct](../standard-library/moneypunct-class.md)의 모든 특수화에 공통 된 열거형 및 구조체를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>주의

구조체 패턴의 배열 필드 요소에서 가능한 값을 설명 하는 열거형 `part`입니다. @No__t_0 값은 다음과 같습니다.

- `none`는 0 개 이상의 공백을 찾거나 아무것도 생성 하지 않습니다.

- 양수 또는 음수 기호를 일치 또는 생성 `sign` 합니다.

- 0 개 이상의 공백과 일치 하거나 공백을 생성 하는 `space` 합니다.

- 통화 기호를 일치 또는 생성 `symbol` 합니다.

- 통화 값을 일치 또는 생성 `value` 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
