---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 20efdc755b7f706fc6ee962daa32bd352df39d45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159771"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

외부 파일에 저장된 시퀀스에 대한 Iostreams 작업을 지원하는 여러 클래스를 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <fstream>
```

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|형식 `basic_filebuf` 에서 특수화 된 **char** 템플릿 매개 변수입니다.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|형식 `basic_fstream` 에서 특수화 된 **char** 템플릿 매개 변수입니다.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|형식 `basic_ifstream` 에서 특수화 된 **char** 템플릿 매개 변수입니다.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|형식 `basic_ofstream` 에서 특수화 된 **char** 템플릿 매개 변수입니다.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|형식 `basic_fstream` 에서 특수화 된 **wchar_t** 템플릿 매개 변수입니다.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|형식 `basic_ifstream` 에서 특수화 된 **wchar_t** 템플릿 매개 변수입니다.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|형식 `basic_ofstream` 에서 특수화 된 **wchar_t** 템플릿 매개 변수입니다.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|형식 `basic_filebuf` 에서 특수화 된 **wchar_t** 템플릿 매개 변수입니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|템플릿 클래스는 외부 파일에 저장된 요소의 시퀀스에서 나가고 들어오는 `Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명하며, 해당 문자 특성은 `Tr` 클래스로 결정됩니다.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|이 템플릿 클래스의 요소 삽입 및 추출을 제어 하는 개체 및 클래스의 스트림 버퍼를 사용 하 여 인코딩된 개체 설명 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**,  **Tr**>, 형식의 요소를 사용 하 여 `Elem`에서 문자 특성이 클래스에 의해 결정 됩니다 `Tr`합니다.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|요소의 추출을 제어 하는 개체 및 클래스의 스트림 버퍼에서 인코딩된 개체를 설명 하는 템플릿 클래스 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, 형식의 요소가 있는 `Elem`에서 문자 특성이 클래스에 의해 결정 됩니다 `Tr`합니다.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|클래스의 스트림 버퍼에 요소 삽입을 제어 하는 개체 및 인코드된 개체를 설명 하는 템플릿 클래스 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, 형식의 요소가 있는 `Elem`에서 문자 특성이 클래스에 의해 결정 됩니다 `Tr`합니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
