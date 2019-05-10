---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: 72b96c300aba1729823462ce6671e2f9a5285761
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412269"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

할당 된 배열에 저장 된 시퀀스에 대 한 iostreams 작업을 지 원하는 여러 클래스를 정의 **char** 개체입니다. 이러한 시퀀스는 C 문자열로/에서 쉽게 변환됩니다.

## <a name="syntax"></a>구문

```cpp
#include <strstream>
```

## <a name="remarks"></a>설명

`strstream` 형식의 개체는 C 문자열인 `char` *로 작업합니다. [basic_string](../standard-library/basic-string-class.md) 형식의 개체로 작업하려면 [\<sstream>](../standard-library/sstream.md)을 사용합니다.

> [!NOTE]
> 클래스 \<strstream >는 사용 되지 않습니다. 클래스를 사용 하는 것이 좋습니다 \<sstream > 대신 합니다.

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[strstreambuf 클래스](../standard-library/strstreambuf-class.md)|에 저장 된 요소의 시퀀스에서 요소의 전송을 제어 하는 스트림 버퍼를 설명 하는 클래스를 **char** 배열 개체입니다.|
|[istrstream 클래스](../standard-library/istrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에서 요소 및 인코드된 개체 추출을 제어하는 개체를 설명합니다.|
|[ostrstream 클래스](../standard-library/ostrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼로 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.|
|[strstream 클래스](../standard-library/strstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼를 사용한 요소 및 인코드된 개체 삽입 및 추출을 제어하는 개체를 설명합니다.|

## <a name="see-also"></a>참고자료

[\<strstream>](../standard-library/strstream.md)<br/>
[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
