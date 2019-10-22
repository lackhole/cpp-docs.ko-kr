---
title: '&lt;ostream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: 3838e215ffac42ec6902ab6a9837f638153cf184
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689159"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

Iostreams에 대 한 삽입을 중재 하는 클래스 템플릿 [basic_ostream](../standard-library/basic-ostream-class.md)를 정의 합니다. 헤더에서 여러 관련 조작자도 정의합니다. 이 헤더는 일반적으로 다른 iostreams 헤더에 의해 포함되며, 직접 포함해야 하는 경우는 거의 없습니다.

## <a name="syntax"></a>구문

```cpp
#include <ostream>
```

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Char에서 특수화 된 `basic_ostream`에서 **문자 및 `char_traits`** 특수화 된 형식을 **만듭니다.**|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|**Wchar_t 및** **wchar_t**에서 특수화 된 `char_traits` `basic_ostream`에서 형식을 만듭니다.|

### <a name="manipulators"></a>조작자

|||
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|줄을 종료하고 버퍼를 플러시합니다.|
|[ends](../standard-library/ostream-functions.md#ends)|문자열을 종료합니다.|
|[flush](../standard-library/ostream-functions.md#flush)|버퍼를 플러시합니다.|
|[swap](../standard-library/ostream-functions.md#swap)|왼쪽 `basic_ostream` 개체 매개 변수의 값을 오른쪽 `basic_ostream` 개체 매개 변수의 값으로 교환합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator<<](../standard-library/ostream-operators.md#op_lt_lt)|스트림에 다양한 형식을 씁니다.|

### <a name="classes"></a>클래스

|인스턴스|설명|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|클래스 템플릿은 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어 하는 개체를 설명 합니다.|

## <a name="see-also"></a>참조

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
