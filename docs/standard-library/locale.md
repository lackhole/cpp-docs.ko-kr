---
title: '&lt;locale&gt;'
ms.date: 11/04/2016
f1_keywords:
- <locale>
- locale/std::<locale>
- std::<locale>
helpviewer_keywords:
- locale header
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
ms.openlocfilehash: 708184a6a6a443456f0d70f57b6be17b281ac4f5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453914"
---
# <a name="ltlocalegt"></a>&lt;locale&gt;

문자 분류 및 문자열 데이터 정렬에 대한 국제 지원을 포함하여, C++ 프로그램이 숫자, 통화, 달력 데이터의 표시 및 서식 지정에 관한 다양한 문화적 규약을 캡슐화하고 조작하기 위해 사용할 수 있는 템플릿 클래스와 함수를 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <locale>
```

### <a name="functions"></a>함수

|기능|Description|
|-|-|
|[has_facet](../standard-library/locale-functions.md#has_facet)|특정 패싯이 지정된 로캘에 저장되었는지를 테스트합니다.|
|[isalnum](../standard-library/locale-functions.md#isalnum)|로캘의 요소가 알파벳인지 또는 숫자인지를 테스트합니다.|
|[isalpha](../standard-library/locale-functions.md#isalpha)|로캘의 요소가 영문자인지를 테스트합니다.|
|[iscntrl](../standard-library/locale-functions.md#iscntrl)|로캘의 요소가 제어 문자인지를 테스트합니다.|
|[isdigit](../standard-library/locale-functions.md#isdigit)|로캘의 요소가 숫자인지를 테스트합니다.|
|[isgraph](../standard-library/locale-functions.md#isgraph)|로캘의 요소가 영숫자인지 문장 부호인지를 테스트합니다.|
|[islower](../standard-library/locale-functions.md#islower)|로캘의 요소가 소문자인지를 테스트합니다.|
|[isprint](../standard-library/locale-functions.md#isprint)|로캘의 요소가 인쇄 가능한 문자인지를 테스트합니다.|
|[ispunct](../standard-library/locale-functions.md#ispunct)|로캘의 요소가 문장 부호 문자인지를 테스트합니다.|
|[isspace](../standard-library/locale-functions.md#isspace)|로캘의 요소가 공백 문자인지를 테스트합니다.|
|[isupper](../standard-library/locale-functions.md#isupper)|로캘의 요소가 대문자인지를 테스트합니다.|
|[isxdigit](../standard-library/locale-functions.md#isxdigit)|로캘의 요소가 16자 숫자를 나타내는 데 사용되는 문자인지를 테스트합니다.|
|[tolower](../standard-library/locale-functions.md#tolower)|문자를 소문자로 변환합니다.|
|[toupper](../standard-library/locale-functions.md#toupper)|문자를 대문자로 변환합니다.|
|[use_facet](../standard-library/locale-functions.md#use_facet)|로캘에 저장된 지정된 형식의 패싯에 대한 참조를 반환합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[codecvt](../standard-library/codecvt-class.md)|내부 및 외부 문자 인코딩 간 변환에 사용된 패싯을 제공하는 템플릿 클래스입니다.|
|[codecvt_base](../standard-library/codecvt-base-class.md)|로 `result`참조 되는 열거형을 정의 하는 데 사용 되는 codecvt 클래스에 대 한 기본 클래스입니다 .이 클래스는 변환 결과를 나타내기 위해 패싯 멤버 함수에 대 한 반환 형식으로 사용 됩니다.|
|[codecvt_byname](../standard-library/codecvt-byname-class.md)|지정된 로캘의 데이터 정렬 패싯으로 사용할 수 있는 개체를 설명하는 파생된 템플릿 클래스입니다. 이 클래스를 사용하여 변환과 관련된 문화 영역별 정보를 검색할 수 있습니다.|
|[collate](../standard-library/collate-class.md)|문자열 정렬 규약을 처리하는 패싯을 제공하는 데이터 정렬 템플릿 클래스입니다.|
|[collate_byname](../standard-library/collate-byname-class.md)|지정된 로캘의 데이터 정렬 패싯으로 사용할 수 있는 개체를 설명하는 파생된 템플릿 클래스입니다. 이 클래스를 사용하여 문자열 정렬 규약과 관련된 문화 영역별 정보를 검색할 수 있습니다.|
|[ctype](../standard-library/ctype-class.md)|문자를 분류하고, 대문자와 소문자 사이에서 변환하고, 네이티브 문자 집합과 로캘에서 사용하는 문자 집합 사이에서 변환하는 데 사용하는 패싯을 제공하는 템플릿 클래스입니다.|
|[ctype\<char>](../standard-library/ctype-char-class.md)|Char 형식에 대 한 템플릿 클래스 `ctype<CharType>` 의 명시적 특수화 인 클래스입니다 .이 클래스는 **char**형식의 문자에 대 한 다양 한 속성의 특징을 설명 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 합니다.|
|[ctype_base](../standard-library/ctype-base-class.md)|개별적으로 또는 전체 범위 내에서 특성을 분류 또는 테스트하는 데 사용하는 열거형을 정의하는 데 사용하는 ctype 클래스의 기본 클래스입니다.|
|[ctype_byname](../standard-library/ctype-byname-class.md)|지정된 로캘의 ctype 패싯으로 사용할 수 있는 개체를 설명하는 파생된 템플릿 클래스입니다. 이 클래스를 사용하여 특성을 분류하고 대/소문자 간 변환하거나 네이티브 및 로캘 지정 문자 집합 사이에서 변환할 수 있습니다.|
|[locale](../standard-library/locale-class.md)|문화별 정보를 특정 지역별 환경을 전체적으로 정의하는 패싯 집합으로 캡슐화하는 로캘 개체에 대해 설명하는 클래스입니다.|
|[messages](../standard-library/messages-class.md)|지정된 로캘에 대한 국제화된 메시지의 카탈로그에서 지역화된 메시지를 검색하기 위해 로캘 패싯으로 사용할 수 있는 개체에 대해 설명하는 템플릿 클래스입니다.|
|[messages_base](../standard-library/messages-base-class.md)|메시지 카탈로그에 대 한 **int** 형식을 설명 하는 기본 클래스입니다.|
|[messages_byname](../standard-library/messages-byname-class.md)|지정된 로캘의 메시지 패싯으로 사용하여 지역화된 메시지를 검색할 수 있는 개체에 대해 설명하는 파생된 템플릿 클래스입니다.|
|[money_base](../standard-library/money-base-class.md)|개별적으로 또는 전체 범위 내에서 특성을 분류 또는 테스트하는 데 사용하는 열거형을 정의하는 데 사용하는 ctype 클래스의 기본 클래스입니다.|
|[money_get](../standard-library/money-get-class.md)|**Chartype** 형식의 시퀀스에서 통화 값으로의 변환을 제어 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[money_put](../standard-library/money-put-class.md)|통화 값에서 **Chartype**형식의 시퀀스로 변환을 제어 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[moneypunct](../standard-library/moneypunct-class.md)|통화 입력 필드 또는 통화 출력 필드를 나타내는 데 사용 되는 **Chartype** 형식의 시퀀스를 설명 하는 데 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[moneypunct_byname](../standard-library/moneypunct-byname-class.md)|지정된 로캘의 moneypunct 패싯으로 사용하여 통화 입력 또는 출력 필드의 서식을 지정할 수 있는 개체에 대해 설명하는 파생된 템플릿 클래스입니다.|
|[num_get](../standard-library/num-get-class.md)|**Chartype** 형식의 시퀀스에서 숫자 값으로의 변환을 제어 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[num_put](../standard-library/num-put-class.md)|숫자 값을 **Chartype**형식의 시퀀스로 변환 하는 것을 제어 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[numpunct](../standard-library/numpunct-class.md)|숫자 및 부울 식의 서식 지정 및 문장 부호에 대 한 정보를 나타내는 데 사용 되는 **Chartype** 형식의 시퀀스를 설명 하는 로컬 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[numpunct_byname](../standard-library/numpunct-byname-class.md)|지정된 로캘의 moneypunct 패싯으로 사용하여 숫자 및 부울 식의 문장 부호 서식을 지정할 수 있는 개체에 대해 설명하는 파생된 템플릿 클래스입니다.|
|[time_base](../standard-library/time-base-class.md)|템플릿 클래스 time_get의 패싯에 대한 기본 클래스로 사용하는 클래스입니다. 열거형 dateorder와 이 형식의 여러 상수만 정의합니다.|
|[time_get](../standard-library/time-get-class.md)|**Chartype** 형식의 시퀀스에서 시간 값으로의 변환을 제어 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[time_get_byname](../standard-library/time-get-byname-class.md)|Time_get\<**chartype**, **inputiterator**> 형식의 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 파생 된 템플릿 클래스입니다.|
|[time_put](../standard-library/time-put-class.md)|시간 값에서 **Chartype**형식의 시퀀스로 변환을 제어 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 템플릿 클래스입니다.|
|[time_put_byname](../standard-library/time-put-byname-class.md)|`time_put` **Chartype**, **outputiterator**> 형식의 \<로캘 패싯으로 사용할 수 있는 개체를 설명 하는 파생 된 템플릿 클래스입니다.|
|[wbuffer_convert 클래스](../standard-library/wbuffer-convert-class.md)|바이트 스트림 버퍼에서 나가고 들어오는 요소의 전송을 제어하는 스트림 버퍼에 대해 설명합니다.|
|[wstring_convert 클래스](../standard-library/wstring-convert-class.md)|와이드 문자열과 바이트 문자열 간의 변환을 수행하는 템플릿 클래스입니다.|

## <a name="see-also"></a>참고자료

[코드 페이지](../c-runtime-library/code-pages.md)\
[로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
