---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: ecf8499a07f03c00588e7b7fd83b8d41a23e8e7a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459094"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

**Char** 개체의 할당 된 배열에 저장 된 시퀀스에 대 한 iostreams 작업을 지 원하는 여러 클래스를 정의 합니다. 이러한 시퀀스는 C 문자열로/에서 쉽게 변환됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<strstream >

**네임스페이스:** std

## <a name="remarks"></a>설명

`strstream` 형식의 개체는 C 문자열인 `char` *로 작업합니다. [basic_string](../standard-library/basic-string-class.md) 형식의 개체로 작업하려면 [\<sstream>](../standard-library/sstream.md)을 사용합니다.

> [!NOTE]
> Strstream > \<의 클래스는 더 이상 사용 되지 않습니다. 대신 sstream >의 \<클래스를 사용 하는 것이 좋습니다.

## <a name="members"></a>멤버

### <a name="classes"></a>클래스

|||
|-|-|
|[strstreambuf 클래스](../standard-library/strstreambuf-class.md)|이 클래스는 **char** 배열 개체에 저장 된 요소의 시퀀스에서의 요소 전송을 제어 하는 스트림 버퍼를 설명 합니다.|
|[istrstream 클래스](../standard-library/istrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에서 요소 및 인코드된 개체 추출을 제어하는 개체를 설명합니다.|
|[ostrstream 클래스](../standard-library/ostrstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼로 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.|
|[strstream 클래스](../standard-library/strstream-class.md)|이 클래스는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼를 사용한 요소 및 인코드된 개체 삽입 및 추출을 제어하는 개체를 설명합니다.|

### <a name="functions"></a>함수

```cpp
void freeze(bool freezefl = true);
char* str();
int pcount();
```

## <a name="see-also"></a>참고자료

[\<strstream>](../standard-library/strstream.md)\
[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
