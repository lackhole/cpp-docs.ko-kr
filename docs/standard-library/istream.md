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
ms.openlocfilehash: 2e39c0de5b11c9aa0a4c69f0142841469ef798c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413283"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

iostreams에 대한 추출을 중재하는 템플릿 클래스 basic_istream 및 삽입과 추출을 모두 중재하는 템플릿 클래스 basic_iostream을 정의합니다. 헤더에서 관련 조작자도 정의합니다. 이 헤더 파일은 일반적으로 다른 iostreams 헤더에 의해 포함되며, 직접 포함해야 하는 경우는 거의 없습니다.

## <a name="syntax"></a>구문

```cpp
#include <istream>
```

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|형식 `basic_iostream` 에서 특수화 된 **char**합니다.|
|[istream](../standard-library/istream-typedefs.md#istream)|형식 `basic_istream` 에서 특수화 된 **char**합니다.|
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

|클래스|설명|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|입력과 출력을 둘 다 수행할 수 있는 스트림 클래스입니다.|
|[basic_istream](../standard-library/basic-istream-class.md)|요소의 추출을 제어 하는 개체 및 형식의 요소가 있는 스트림 버퍼에서 인코딩된 개체를 설명 하는 템플릿 클래스 `Elem`이 라고도 [char_type](../standard-library/basic-ios-class.md#char_type), 문자 특성이 클래스에 의해 결정 됩니다 `Tr`이 라고도 [traits_type](../standard-library/basic-ios-class.md#traits_type)합니다.|

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
