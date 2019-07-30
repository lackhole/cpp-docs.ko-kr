---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: ba6a4152b8d37f5b0186f9d05c6ba850e8c2e54c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454015"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

외부 파일에 저장된 시퀀스에 대한 Iostreams 작업을 지원하는 여러 클래스를 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <fstream>
```

### <a name="typedefs"></a>형식 정의

|형식 이름|Description|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Char 템플릿 `basic_filebuf` 매개 변수  에서 특수화 된 형식입니다.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Char 템플릿 `basic_fstream` 매개 변수  에서 특수화 된 형식입니다.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Char 템플릿 `basic_ifstream` 매개 변수  에서 특수화 된 형식입니다.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Char 템플릿 `basic_ofstream` 매개 변수  에서 특수화 된 형식입니다.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Wchar_t 템플릿 `basic_fstream` 매개 변수  에서 특수화 된 형식입니다.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Wchar_t 템플릿 `basic_ifstream` 매개 변수  에서 특수화 된 형식입니다.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Wchar_t 템플릿 `basic_ofstream` 매개 변수  에서 특수화 된 형식입니다.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Wchar_t 템플릿 `basic_filebuf` 매개 변수  에서 특수화 된 형식입니다.|

### <a name="classes"></a>클래스

|클래스|Description|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|템플릿 클래스는 외부 파일에 저장된 요소의 시퀀스에서 나가고 들어오는 `Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명하며, 해당 문자 특성은 `Tr` 클래스로 결정됩니다.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|이 템플릿 클래스는 형식의\< `Elem`요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md)**Elem**, **Tr**> 클래스의 스트림 버퍼를 사용 하 여 요소 및 인코드된 개체의 삽입 및 추출을 제어 하는 개체를 설명 합니다. 문자 특성은 클래스 `Tr`에 의해 결정 됩니다.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|이 템플릿 클래스는 문자 특성이 있는 `Elem`형식의 요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> 클래스의 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어 하는 개체를 설명 합니다. 클래스 `Tr`에 의해 결정 됩니다.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|이 템플릿 클래스는 문자 특성이 있는 `Elem`형식의 요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> 클래스의 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어 하는 개체를 설명 합니다. 클래스 `Tr`에 의해 결정 됩니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
