---
title: iostreams 규칙
ms.date: 11/04/2016
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
ms.openlocfilehash: 222a65f60b231ba4b3768131c15d6e0d736f211e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449011"
---
# <a name="iostreams-conventions"></a>iostreams 규칙

iostreams 헤더는 텍스트와 인코드된 형식 간 변환 및 외부 파일에 대한 입력과 출력을 지원합니다.

|||
|-|-|
|[\<fstream>](../standard-library/fstream.md)|[\<iomanip>](../standard-library/iomanip.md)|
|[\<ios>](../standard-library/ios.md)|[\<iosfwd>](../standard-library/iosfwd.md)|
|[\<iostream>](../standard-library/iostream.md)|[\<istream>](../standard-library/istream.md)|
|[\<ostream>](../standard-library/ostream.md)|[\<sstream>](../standard-library/sstream.md)|
|[\<streambuf>](../standard-library/streambuf.md)|[\<strstream>](../standard-library/strstream.md)|

가장 간단하게 iostreams를 사용하려면 [\<iostream>](../standard-library/iostream.md) 헤더를 포함하기만 하면 됩니다. 그런 다음 [cin](../standard-library/iostream.md#cin) 또는 [wcin](../standard-library/iostream.md#wcin)에서 값을 추출하여 표준 입력을 읽을 수 있습니다. 이 작업을 수행하는 규칙은 [basic_istream 클래스](../standard-library/basic-istream-class.md)에 대한 설명에 간략하게 나와 있습니다. [cout](../standard-library/iostream.md#cout) 또는 [wcout](../standard-library/iostream.md#wcout)에 값을 삽입하여 표준 출력을 쓸 수도 있습니다. 이 작업을 수행하는 규칙은 [basic_ostream 클래스](../standard-library/basic-ostream-class.md)에 대한 설명에 간략하게 나와 있습니다. 추출기와 삽입기에 공통된 형식 제어는 [basic_ios 클래스](../standard-library/basic-ios-class.md)에 의해 관리됩니다. 개체 추출 및 삽입을 가장하여 이 형식 정보를 조작하는 것이 여러 조작자의 영역입니다.

[\<fstream>](../standard-library/fstream.md)에 선언된 클래스를 사용하면 이름으로 연 파일에서 동일한 iostreams 작업을 수행할 수 있습니다. iostreams와 [basic_string 클래스](../standard-library/basic-string-class.md) 클래스의 개체 간에 변환하려면 [\<sstream>](../standard-library/sstream.md)에 선언된 클래스를 사용합니다. C 문자열에서 동일한 작업을 수행하려면 [\<strstream>](../standard-library/strstream.md)에 선언된 클래스를 사용합니다.

나머지 헤더는 지원 서비스를 제공하는데, 이 서비스는 일반적으로 iostreams 클래스의 고급 사용자만 직접적인 관심을 보입니다.

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
