---
title: 기본 형식 (C++)
ms.date: 11/04/2016
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: f4af392ed559349b0e49fd26f3ecb4406a70b74b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153803"
---
# <a name="fundamental-types--c"></a>기본 형식 (C++)

C++의 기본 형식은 정수 계열, 부동 소수점 및 void의 세 가지 범주로 구분됩니다. 정수 계열 형식은 정수를 처리할 수 있습니다. 부동 소수점 형식은 소수 부분이 있을 수 있는 값을 지정할 수 있습니다.

[void](../cpp/void-cpp.md) 형식은 빈 값 집합을 설명합니다. 형식의 변수가 없기 **void** 지정할 수 있습니다-값을 반환 하는 함수를 선언 하는 데 주로 사용 됩니다 또는 형식화 된 데이터 또는 임의로 형식화 되지 제네릭 포인터를 선언 하 합니다. 명시적으로 변환 하거나 형식으로 캐스팅할 수 식일 **void**합니다. 그러나 이러한 식은 사용이 다음으로 제한됩니다.

- 식 문. 자세한 내용은 [식](../cpp/expressions-cpp.md)을 참조하세요.

- 쉼표 연산자의 왼쪽 피연산자. 자세한 내용은 [쉼표 연산자](../cpp/comma-operator.md) 를 참조하세요.

- 조건 연산자의 두 번째 또는 세 번째 피연산자(`? :`)입니다. 자세한 내용은 [조건 연산자를 사용하는 식](../cpp/conditional-operator-q.md) 를 참조하세요.

다음 표에서는 형식 크기에 대한 제한을 설명합니다. 이러한 제한은 Microsoft 구현과 무관합니다.

### <a name="fundamental-types-of-the-c-language"></a>C++ 언어의 기본 형식

|범주|형식|목차|
|--------------|----------|--------------|
|정수 계열|**char**|형식 **char** 일반적으로 기본 실행 문자 집합의 멤버를 포함 하는 정수 계열 형식-기본적으로 Microsoft에서는 ASCII입니다 C++합니다.<br /><br /> C++ 컴파일러는 형식의 변수에 처리 **char**를 **char 서명**, 및 **unsigned char** 서로 다른 형식으로 합니다. 형식의 변수에 **char** 올려진 **int** 형식인 것 처럼 **char 서명** 기본적으로 /J 컴파일 옵션을 사용 하지 않으면. 이 경우 형식으로 처리 되므로 **unsigned char** 로 승격 됩니다 **int** 부호 확장 없이 합니다.|
||**bool**|형식 **bool** 두 값 중 하나를 가질 수 있는 정수 계열 형식인 **true** 하거나 **false**합니다. 크기는 지정되지 않습니다.|
||**short**|형식 **short int** (또는 단순히 **짧은**) 형식의 크기 보다 크거나 같은 경우에 정수 계열 형식인 **char**, 및 보다 작거나 형식의크기**int**합니다.<br /><br /> 형식의 개체 **짧은** 로 선언할 수 있습니다 **짧은 서명** 하거나 **unsigned short**합니다. **즉 서명** 에 대 한 동의어가 **짧은**합니다.|
||**int**|형식 **int** 형식의 크기 보다 크거나 같은 경우에 정수 계열 형식인 **short int**, 및 보다 작거나 형식의 크기 **긴**합니다.<br /><br /> 형식의 개체 **int** 로 선언할 수 있습니다 **int 서명** 하거나 **부호 없는 int**합니다. **Int 서명** 에 대 한 동의어가 **int**합니다.|
||**__int8**, **__int16**, **__int32**, **__int64**|크기가 지정된 정수 `__int n`입니다. 여기서 `n` 은 정수 변수의 크기(비트)입니다. **__int8**, **__int16**합니다 **__int32** 하 고 **__int64** 은 Microsoft 전용 키워드입니다. 모든 형식이 아닌 모든 아키텍처에서 사용할 수 있습니다. (**__int128** 지원 되지 않습니다.)|
||**long**|형식 **긴** (또는 **long int**) 형식의 크기 보다 크거나 같은 경우에 정수 계열 형식인 **int**합니다.<br /><br /> 형식의 개체 **긴** 로 선언할 수 있습니다 **기호가 있는 long** 하거나 **부호 없는 long**합니다. **기호가 있는 long** 에 대 한 동의어가 **긴**합니다.|
||**long long**|부호 없는 보다 큰 **긴**합니다.<br /><br /> 형식의 개체 **long long** 로 선언할 수 있습니다 **기호가 있는 long long** 하거나 **부호 없는 long long**합니다. **기호가 있는 long long** 에 대 한 동의어가 **long long**합니다.|
||**wchar_t**, **__wchar_t**|형식 변수의 **wchar_t** 는 와이드 문자 또는 멀티 바이트 문자 형식을 지정 합니다. 기본적으로 **wchar_t** 는 네이티브 형식에 사용할 수 있지만 [/zc: wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 되도록 **wchar_t** 에 대 한 typedef **unsigned short**합니다. 합니다 **__wchar_t** 네이티브에 대 한 Microsoft 전용 동의어 **wchar_t** 형식입니다.<br /><br /> 문자 또는 문자열 리터럴 앞에 L 접두사를 사용하여 와이드 문자 형식을 지정합니다.|
|부동 소수점|**float**|형식 **float** 가장 작은 부동 소수점 형식입니다.|
||**double**|형식 **이중** 보다 큰 부동 소수점 형식 또는 형식 **float**, 하지만 보다 작거나 형식의 크기 **long double**합니다.<br /><br /> Microsoft 전용: 표현의 **long double** 하 고 **double** 동일 합니다. 그러나 **long double** 하 고 **double** 은 별개 형식입니다.|
||**long double**|형식 **long double** 부동 소수점 형식 보다 큰 또는 형식 **double**합니다.|

**Microsoft 전용**

다음 표에서는 Microsoft C++의 기본 형식에 필요한 스토리지 크기를 나열합니다.

### <a name="sizes-of-fundamental-types"></a>기본 형식의 크기

|형식|크기|
|----------|----------|
|**bool**, **char**, **unsigned char**, **signed char**, **__int8**|1바이트|
|**__int16**, **short**, **unsigned short**, **wchar_t**, **__wchar_t**|2바이트|
|**부동 소수점**, **__int32**, **int**를 **부호 없는 int**를 **긴**, **부호 없는 long**|4바이트|
|**double**, **__int64**, **long double**, **long long**|8바이트|

**Microsoft 전용 종료**

각 형식의 값 범위에 대한 요약은 [데이터 형식 범위](../cpp/data-type-ranges.md) 를 참조하세요.

형식 변환에 대한 자세한 내용은 [표준 변환](../cpp/standard-conversions.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 형식 범위](../cpp/data-type-ranges.md)