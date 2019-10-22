---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 1f85367b9ae527c9387d085acc1496bfbbf7cc9e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688033"
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
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|**문자** 템플릿 매개 변수에서 특수화 된 형식 `basic_filebuf` 합니다.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|**문자** 템플릿 매개 변수에서 특수화 된 형식 `basic_fstream` 합니다.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|**문자** 템플릿 매개 변수에서 특수화 된 형식 `basic_ifstream` 합니다.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|**문자** 템플릿 매개 변수에서 특수화 된 형식 `basic_ofstream` 합니다.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_fstream` 합니다.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_ifstream` 합니다.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_ofstream` 합니다.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_filebuf` 합니다.|

### <a name="classes"></a>클래스

|인스턴스|설명|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|클래스 템플릿은 `Elem` 형식의 요소 전송을 제어 하는 스트림 버퍼를 설명 합니다. 해당 문자 특성은 외부 파일에 저장 된 요소의 시퀀스를 대상으로 하 `Tr` 클래스에 의해 결정 됩니다.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|클래스 템플릿은 `Elem` 형식의 요소가 포함 된 [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> 클래스의 스트림 버퍼를 사용 하 여 요소 및 인코드된 개체의 삽입 및 추출을 제어 하는 개체를 설명 합니다. 해당 문자는 특성은 클래스 `Tr`에 의해 결정 됩니다.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|클래스 템플릿에서는 문자 특성이 `Elem` 형식의 요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> 클래스의 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어 하는 개체를 설명 합니다. 클래스 `Tr`에 의해 결정 됩니다.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|클래스 템플릿은 문자 특성이 결정 되는 `Elem` 형식의 요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> 클래스의 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어 하는 개체를 설명 합니다. 클래스 `Tr`.|

## <a name="see-also"></a>참조

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
