---
title: '&lt;istream&gt;'
ms.date: 11/04/2016
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
ms.openlocfilehash: 8e9675a673462c8eaab94d29a3ae36a4786737b7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687848"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

Iostreams 대해 추출를 중재 하는 클래스 템플릿 basic_istream 및 삽입과 중재 모두를 추출 하는 클래스 템플릿 basic_iostream를 정의 합니다. 헤더에서 관련 조작자도 정의합니다. 이 헤더 파일은 일반적으로 다른 iostreams 헤더에 의해 포함되며, 직접 포함해야 하는 경우는 거의 없습니다.

## <a name="syntax"></a>구문

```cpp
#include <istream>
```

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|**Char**에 특수화 된 형식 `basic_iostream`입니다.|
|[istream](../standard-library/istream-typedefs.md#istream)|**Char**에 특수화 된 형식 `basic_istream`입니다.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|**wchar**에서 특수화된 `basic_iostream` 형식입니다.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|**wchar**에서 특수화된 `basic_istream` 형식입니다.|

### <a name="manipulators"></a>조작자

|||
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|스트림의 공백을 건너뜁니다.|
|[swap](../standard-library/istream-functions.md#istream_swap)|두 스트림 개체를 교환합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator>>](../standard-library/istream-operators.md#op_gt_gt)|스트림에서 문자 및 문자열을 추출합니다.|

### <a name="classes"></a>클래스

|인스턴스|설명|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|입력과 출력을 둘 다 수행할 수 있는 스트림 클래스입니다.|
|[basic_istream](../standard-library/basic-istream-class.md)|클래스 템플릿은 [char_type](../standard-library/basic-ios-class.md#char_type)라고도 하는 `Elem` 형식의 요소를 사용 하 여 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어 하는 개체를 설명 합니다. 해당 문자 특성은 클래스 `Tr` [에 의해 결정 됩니다. traits_type](../standard-library/basic-ios-class.md#traits_type).|

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
