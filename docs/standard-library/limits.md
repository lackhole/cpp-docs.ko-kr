---
title: '&lt;limits&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: 3ad740975cfff4f65f9e1c800a709cfaca3367db
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687816"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

클래스 템플릿 `numeric_limits`와 부동 소수점 표현 및 반올림과 관련 된 두 개의 열거형을 정의 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<limits>

**네임스페이스:** std

## <a name="remarks"></a>주의

@No__t_0 클래스의 명시적 특수화는 문자, 정수, 부동 소수점 형식 및 **bool** C++ 을 포함 하 여 기본 형식의 많은 속성을 설명 합니다. 언어도. \<limits>에 설명된 속성에는 정확도, 최소 및 최대 크기 표현, 반올림 및 신호 형식 오류가 포함됩니다.

## <a name="members"></a>멤버

### <a name="enumerations"></a>열거형

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|이 열거형은 구현에서 비정규화된 부동 소수점 값(너무 작아서 정규화된 값으로 나타낼 수 없는 값)을 나타내기 위해 선택할 수 있는 다양한 메서드를 설명합니다.|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|이 열거형은 구현에서 부동 소수점 값을 정수 값으로 반올림하기 위해 선택할 수 있는 다양한 메서드를 설명합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[numeric_limits 클래스](../standard-library/numeric-limits-class.md)|클래스 템플릿은 기본 제공 숫자 형식의 산술 속성을 설명 합니다.|

## <a name="see-also"></a>참조

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
