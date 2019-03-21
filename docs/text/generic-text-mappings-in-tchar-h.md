---
title: tchar.h의 제네릭 텍스트 매핑
ms.date: 11/04/2016
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
ms.openlocfilehash: 779702aa33e2aa24bf5a380bd8435745cc0aadbd
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822641"
---
# <a name="generic-text-mappings-in-tcharh"></a>tchar.h의 제네릭 텍스트 매핑

세계적으로 사용되는 문자열 관련 코드 전송을 단순하게 하기 위해 Microsoft 런타임 라이브러리에는 다양한 데이터 형식과 루틴, 기타 개체들에 대한 Microsoft만의 특화된 제네릭 텍스트 매핑용 도구가 있습니다. tchar.h에 정의되어 있는 이러한 매핑 도구는 `#define`된 매니페스트 상수에 따라 싱글, 멀티바이트 및 유니코드 문자 집합에 관계없이 컴파일됩니다. 이러한 제네릭 텍스트 매핑은 ANSI 표준과 호환되지 않는 Microsoft 확장입니다.

tchar.h를 사용하여 같은 소스 코드를 가지고 싱글, 멀티바이트 문자 집합(MBCS)뿐만 아니라 유니코드 기반 애플리케이션을 빌드할 수 있습니다. `_tcs` 접두어를 가지고 있는 tchar.h에 정의되어 있는 매크로는 전처리기 정의에 따라 적절하게 `str`, `_mbs`나 `wcs` 계열 함수를 호출합니다. MBCS로 빌드하려면 `_MBCS` 상수를, 유니코드로 빌드하려면 `_UNICODE` 상수를 정의합니다. 싱글바이트 응용 프로그램을 빌드하려면 이 두가지를 정의하지 않습니다. MFC 응용 프로그램에서는 `_UNICODE`가 기본적으로 정의됩니다.

`_TCHAR` 데이터 형식은 tchar.h에서 조건에 따라 정의가 달라집니다. `_UNICODE`가 정의되어 있다면 `_TCHAR`은 **wchar_t**로 정의되고, 만일 싱글바이트 및 멀티바이트 문자 집합(MBCS) 기반의 빌드라면 **char**로 정의됩니다. (**wchar_t**는 기본 유니코드 와이드 문자 데이터 형식입니다. 이것은 8비트의 부호 있는 **char**이 짝을 이룬 16비트입니다.) 세계적으로 사용되는 애플리케이션 개발을 위해 바이트가 아닌 `_TCHAR` 단위를 사용하는 `_tcs` 함수군을 사용하세요. 예를 들어 `_tcsncpy` 함수가 복사하는 단위는 `n` 바이트가 아닌 `_TCHARs`입니다.

일부 단일 바이트 문자 집합(SBCS) 문자열 처리 함수는 매개변수로 signed `char*` 형식을 받기 때문에 `_MBCS`가 정의되어 있다면 컴파일러 경고가 발생합니다. 이 경고를 방지할 수 있는 3가지 방법이 있습니다.

1. tchar.h에 구현된 형식에 안전한 인라인 타입의 작은 함수(thunk)를 사용합니다. 이는 기본 동작입니다.

1. 명령줄에서 `_MB_MAP_DIRECT`를 정의하여 tchar.h의 매크로를 직접 사용하십시오. 이렇게 하려면 형식을 수동으로 일치시켜야 합니다. 가장 빠른 방법이지만 형식이 안전하지 않습니다.

1. tchar.h에 구현된 정적 라이브러리의 형식에 안전한 인라인 타입 작은 함수(thunk)를 사용합니다. 이렇게 하려면 명령줄에서 `_NO_INLINING` 상수를 정의합니다. 이는 속도가 가장 느리지만 형식이 가장 안전 방법입니다.

### <a name="preprocessor-directives-for-generic-text-mappings"></a>일반 텍스트 매핑용 전처리기 지시문

|# 정의|컴파일 버전|예제|
|---------------|----------------------|-------------|
|`_UNICODE`|유니코드(와이드 문자)|`_tcsrev`는 `_wcsrev`에 매핑됩니다.|
|`_MBCS`|멀티바이트 문자|`_tcsrev`는 `_mbsrev`에 매핑됩니다.|
|None (`_UNICODE`나 `_MBCS`가 정의되지 않음. 기본값.)|SBCS(ASCII)|`_tcsrev`는 `strrev`에 매핑됩니다.|

예를 들어, tchar.h에 정의된 제네릭 텍스트 함수 `_tcsrev`는 `_MBCS`를 프로그램에서 정의한 경우 `_mbsrev`로 매핑되고, `_UNICODE`를 정의한 경우 `_wcsrev`로 매핑됩니다. 그렇지 않으면 `_tcsrev`가 `strrev`로 매핑됩니다. 프로그래밍 편의를 위해 tchar.h에서 제공하는 다른 데이터 유형 매핑을 사용할 수 있지만 `_TCHAR``이 가장 유용합니다.

### <a name="generic-text-data-type-mappings"></a>일반 텍스트 데이터 형식 매핑

|일반 텍스트<br /> 데이터 형식|_UNICODE &AMP;<br /> _MBCS 정의되지 않음|_MBCS<br /> 정의됨|_UNICODE<br /> 정의됨|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**char**|**char**|**wchar_t**|
|`_TINT`|**int**|**unsigned int**|`wint_t`|
|`_TSCHAR`|**signed) char**|**signed) char**|**wchar_t**|
|`_TUCHAR`|**unsigned char**|**unsigned char**|**wchar_t**|
|`_TXCHAR`|**char**|**unsigned char**|**wchar_t**|
|`_T` 또는 `_TEXT`|효과 없음(전처리기에 의해 제거됨)|효과 없음(전처리기에 의해 제거됨)|`L` (유니코드 문자열로 변환)|

루틴, 변수 및 기타 개체의 제네릭 텍스트 매핑 목록은 런타임 라이브러리 참조의 [제네릭 텍스트 매핑](../c-runtime-library/generic-text-mappings.md)을 참조합니다.

> [!NOTE]
>  유니코드 문자열에는 null 바이트가 포함되어 있기 때문에 `str` 계열 함수군을 사용하면 안 됩니다. 마찬가지로 `wcs` 계열 함수군에 MBCS나 SBCS 문자열을 사용하지 않습니다.

다음 코드 조각은 `_TCHAR` 및 `_tcsrev`를 MBCS, 유니코드 및 SBCS 모델에 매핑하여 사용하는 방법을 보여줍니다.

```cpp
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

`_MBCS`가 정의된 경우 전처리기에 의해 매핑됩니다.

```cpp
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

`_UNICODE`가 정의된 경우 또한, 전처리기에 의해 매핑됩니다.

```cpp
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

`_MBCS`나 `_UNICODE`가 정의되어 있지 않은 경우 전처리기는 다음과 같이 싱글바이트 ASCII 코드로 매핑합니다.

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

따라서 하나의 소스 코드 파일을 작성하고 유지 관리하면 컴파일을 통해 세 가지 문자 집합 중 특정 루틴을 선택적으로 실행할 수 있습니다.

## <a name="see-also"></a>참고자료

[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)<br/>
[_MBCS 코드와 TCHAR.H 데이터 형식 사용](../text/using-tchar-h-data-types-with-mbcs-code.md)
