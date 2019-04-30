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
ms.openlocfilehash: eb73c77f0e2658cf750cf17ca85549a09d1cbe51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370933"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

iostreams에 대한 삽입을 중재하는 템플릿 클래스 [basic_ostream](../standard-library/basic-ostream-class.md)을 정의합니다. 헤더에서 여러 관련 조작자도 정의합니다. 이 헤더는 일반적으로 다른 iostreams 헤더에 의해 포함되며, 직접 포함해야 하는 경우는 거의 없습니다.

## <a name="syntax"></a>구문

```cpp
#include <ostream>
```

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|형식을 만듭니다 `basic_ostream` 에서 특수화 된 **char** 하 고 `char_traits` 에서 특수화 된 **char**합니다.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|형식을 만듭니다 `basic_ostream` 에서 특수화 된 **wchar_t** 하 고 `char_traits` 에서 특수화 된 **wchar_t**합니다.|

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

|클래스|설명|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|이 템플릿 클래스는 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
