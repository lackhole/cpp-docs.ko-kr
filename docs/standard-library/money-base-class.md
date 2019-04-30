---
title: money_base 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: b0c77b523dbe31bc5b07ae3d736441880fe04546
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383570"
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

열거형 `part` 구조체 패턴에서 배열 필드의 요소에 사용 가능한 값에 설명 합니다. 값 `part` 됩니다.

- `none` 0 개 이상의 공백과 일치 시키거나 아무 항목도 생성 됩니다.

- `sign` 검색 하거나 양수 또는 음수 기호를 생성 합니다.

- `space` 0 개 이상의 공백과 일치 시키거나 공백을 생성 합니다.

- `symbol` -일치 시키거나 통화 기호를 생성 합니다.

- `value` -일치 시키거나 통화 값을 생성 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
