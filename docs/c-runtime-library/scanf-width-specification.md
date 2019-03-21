---
title: scanf 너비 사양
ms.date: 11/04/2016
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- scanf
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
ms.openlocfilehash: 1431002a7e7d0054ac20c05c76b05cabc96177c5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743269"
---
# <a name="scanf-width-specification"></a>scanf 너비 사양

이 정보는 `scanf_s`와 같은 보안 버전을 비롯하여 함수의 `scanf` 패밀리에서 형식 문자열의 해석에 적용됩니다. 다음 함수는 일반적으로 입력 스트림이 일련의 토큰으로 나뉜다고 가정합니다. 토큰은 공백(공백, 탭 또는 줄 바꿈)으로 구분되거나 숫자 형식의 경우 숫자 텍스트로 변환할 수 없는 첫 번째 문자가 나타내는 숫자 데이터 형식의 자연스러운 끝으로 구분됩니다. 입력 구문 분석을 토큰의 자연스러운 끝 이전에 중단하는 데 너비 지정을 사용할 수 있습니다.

*width* 지정은 *너비* 필드라고 하는 양의 정수를 포함할 수 있는 형식 필드 한정자와 `%` 사이의 문자 및 필드 형식의 수정자(예: 정수 유형이 **short** 또는 **long**인지 표시)로도 간주할 수 있는 필드의 크기를 나타내는 하나 이상의 문자로 구성되어 있습니다. 이러한 문자를 크기 접두사라고 합니다.

## <a name="the-width-field"></a>너비 필드

*너비* 필드는 해당 필드에서 읽을 최대 문자 수를 제어하는 양의 10진수입니다. 해당 `argument`에는 *너비* 문자보다 적은 수의 문자가 변환되어 저장됩니다. *너비*에 도달하기 전에 공백 문자(공백, 탭 또는 줄바꿈) 또는 지정된 형식에 따라 변환할 수 없는 문자가 발생한 경우 *너비* 문자보다 적은 수의 문자를 읽을 수 있습니다.

너비 지정은 이러한 함수의 보안 버전(즉, `scanf_s`, `wscanf_s` 등)에서 요구하는 버퍼 크기 인수와 별개입니다. 다음 예에서는 너비가 20으로 지정되어 있습니다. 즉, 입력 스트림에서 최대 20자를 읽습니다. 버퍼 길이는 읽을 수 있는 20자와 null 종결자를 위한 공간을 포함한 21입니다.

```C
char str[21];
scanf_s("%20s", str, 21);
```

*너비* 필드가 사용되지 않은 경우 `scanf_s`는 전체 토큰을 문자열로 읽으려고 합니다. 지정된 크기가 작아 전체 토큰을 포함할 수 없는 경우에는 대상 문자열에 아무것도 기록되지 않습니다. *너비* 필드가 지정되어 있으면 토큰의 첫 번째 *너비*자가 null 종결자와 함께 대상 문자열에 기록됩니다.

## <a name="the-size-prefix"></a>크기 접두사

선택적 접두사인 **h**, **l**, **ll**, **I64** 및 **L**은 `argument`(수정하는 형식 문자에 따라 long 또는 short, 단일 바이트 문자 또는 와이드 문자)의 크기를 나타냅니다. 이러한 서식 지정 문자는 `scanf` 또는 `wscanf` 함수의 형식 문자와 함께 사용되어 다음 표에 표시된 것처럼 인수의 해석을 지정합니다. 형식 접두사 **I64**는 Microsoft 확장으로, ANSI와 호환되지 않습니다. 형식 문자 및 해당 의미는 [scanf 형식 필드 문자](../c-runtime-library/scanf-type-field-characters.md)의 "scanf 함수에 대한 형식 문자" 표에 나와 있습니다.

> [!NOTE]
> 데이터 형식 `char`과 함께 사용되는 경우 **h**, **l** 및 **L** 접두사는 Microsoft 확장입니다.

### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>Scanf 및 wscanf 서식-형식 지정자에 대한 크기 접두사

|지정할 함수|접두사 사용|형식 지정자 사용|
|----------------|----------------|-------------------------|
|**double**|**l**|**e**, **E**, **f**, **g** 또는 **G**|
|**long double**(double과 같음)|**L**|**e**, **E**, **f**, **g** 또는 **G**|
|**long int**|**l**|**d**, **i**, **o**, **x** 또는 **X**|
|**long unsigned int**|**l**|**u**|
|**long long**|**ll**|**d**, **i**, **o**, **x** 또는 **X**|
|`short int`|**h**|**d**, **i**, **o**, **x** 또는 **X**|
|**short unsigned int**|**h**|**u**|
|__**int64**|**I64**|**d**, **i**, **o**, **u**, **x** 또는 **X**|
|단일 바이트 문자(`scanf` 사용)|**h**|**c** 또는 **C**|
|단일 바이트 문자(`wscanf` 사용)|**h**|**c** 또는 **C**|
|와이드 문자(`scanf` 사용)|**l**|**c** 또는 **C**|
|와이드 문자(`wscanf` 사용)|**l**|**c** 또는 **C**|
|단일 바이트 문자열(`scanf` 사용)|**h**|**s** 또는 **S**|
|단일 바이트 문자열(`wscanf` 사용)|**h**|**s** 또는 **S**|
|와이드 문자열(`scanf` 사용)|**l**|**s** 또는 **S**|
|와이드 문자열(`wscanf` 사용)|**l**|**s** 또는 **S**|

다음 예에서는 `scanf_s` 함수 및 `wscanf_s` 함수와 함께 **h** 및 **l**를 사용합니다.

```C
scanf_s("%ls", &x, 2);     // Read a wide-character string
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character
```

`scanf` 패밀리에 비보안 함수를 사용하는 경우 이전 인수의 버퍼 길이를 나타내는 크기 매개 변수를 생략합니다.

## <a name="reading-undelimited-strings"></a>구분되지 않은 문자열 읽기

공백 문자로 구분되지 않은 문자열을 읽으려면 대괄호(**[ ]**)로 둘러싸인 문자 집합이 **s**(문자열) 형식 문자를 대신할 수 있습니다. 대괄호로 둘러싸인 문자 집합을 제어 문자열이라고 합니다. 해당 입력된 필드는 제어 문자열에 나타나지 않는 첫 번째 문자까지 읽힙니다. 세트의 첫 번째 문자가 캐럿(**^**)이면 영향이 취소됩니다. 입력 필드는 나머지 문자 세트에 나타나는 첫 번째 문자까지 읽힙니다.

**%[a-z]** 및 **%[z-a]** 는 **%[abcde...z]** 와 동일한 것으로 해석됩니다. 이는 공통 `scanf` 함수 확장이지만 ANSI 표준에는 이러한 확장이 필요하지 않습니다.

## <a name="reading-unterminated-strings"></a>종결되지 않은 문자열 읽기

null 종결 문자('\0')를 저장하지 않고 문자열을 저장하려면 사양 **%**<em>n</em>**c**를 사용합니다. 여기서 *n*은 10진수입니다. 이 경우에 **c** 형식 문자는 인수가 문자 배열에 대한 포인터임을 나타냅니다. 입력 스트림에서 지정된 위치로 다음 *n*개 문자를 읽고 null 문자('\0')는 추가되지 않습니다. *n*이 지정되어 있지 않으면 기본값은 1입니다.

## <a name="when-scanf-stops-reading-a-field"></a>scanf가 필드 읽기를 중지하는 경우

`scanf` 함수는 각 입력 필드를 문자 단위로 검색합니다. 여러 가지 이유로 인해 이 함수가 공백 문자에 도달하기 전에 특정 입력 필드 읽기를 중지할 수 있습니다.

- 지정된 너비에 도달한 경우

- 지정된 대로 다음 문자를 변환할 수 없는 경우

- 다음 문자가 일치해야 하는 제어 문자열의 문자와 충돌하는 경우

- 다음 문자가 지정된 문자 집합에 나타나지 않는 경우

어떤 이유로든 `scanf` 함수가 입력 필드 읽기를 중지한 경우 다음 입력 필드는 읽지 않은 첫 번째 문자에서 시작되는 것으로 간주됩니다. 충돌하는 문자(하나가 있는 경우)는 읽지 않은 것으로 간주되고 다음 입력 필드의 첫 번째 문자 또는 입력 스트림에서 후속 읽기 작업의 첫 번째 문자입니다.

## <a name="see-also"></a>참고 항목

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[형식 사양 필드: scanf 및 wscanf 함수](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)<br/>
[scanf 형식 필드 문자](../c-runtime-library/scanf-type-field-characters.md)<br/>
