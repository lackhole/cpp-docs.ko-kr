---
title: char, wchar_t, char16_t, char32_t
ms.date: 02/14/2018
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
ms.openlocfilehash: 542751cdbd5bb21bb70467163c823e2669373e24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331170"
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t

형식을 **char**, **wchar_t**를 **char16_t** 고 **char32_t** 영숫자 문자를 나타내는 기본 제공 형식인 뿐만 영숫자가 아닌 문자 모양 및 인쇄할 수 없는 문자가 있습니다.

## <a name="syntax"></a>구문

```cpp
char     ch1{ 'a' };  // or { u8'a' }
wchar_t  ch2{ L'a' };
char16_t ch3{ u'a' };
char32_t ch4{ U'a' };
```

## <a name="remarks"></a>설명

합니다 **char** 유형이 되었습니다 C 원래 문자 형식 및 C++합니다. 형식 **unsigned char** 를 나타내는 데 자주를 *바이트*, 기본 제공 형식에 없는 C++. 합니다 **char** 유형은 ISO-8859 문자 집합 및 Shift JIS 등 멀티 바이트 문자의 각 바이트 또는 유니코드 문자 집합을 u t F-8 인코딩 또는 ASCII 문자 집합의 문자를 저장 합니다. 문자열 **char** 형식 이라고 *좁힐* 멀티 바이트 문자를 인코딩하는 데 사용 하는 경우에 문자열입니다. Microsoft 컴파일러에서 **char** 8 비트 형식입니다.

합니다 **wchar_t** 형식이 구현 시 정의 된 와이드 문자 형식입니다. Microsoft 컴파일러에서 u t F-16LE로 인코드된 유니코드입니다. 저장 하는 데 사용 하는 16 비트 와이드 문자를 나타내는 Windows 운영 체제에서 네이티브 문자 형식입니다. 와이드 문자 버전의 유니버설 C 런타임 (UCRT) 라이브러리 함수 사용 **wchar_t** 및 해당 포인터 및 배열 형식 매개 변수 및 반환 값으로 수행으로 네이티브 Windows API의 와이드 문자 버전입니다.

합니다 **char16_t** 하 고 **char32_t** 형식은 16 비트 및 32 비트 와이드 문자를 각각 나타냅니다. Utf-16 형식으로 저장할 수 있습니다으로 인코드된 유니코드 합니다 **char16_t** 유형 및 UTF-32에 저장할 수으로 인코드된 유니코드를 **char32_t** 형식. 이러한 형식의 문자열 및 **wchar_t** 는 모두 라고 *와이드* 문자열, 문자열의 경우에 따라서는에서는 하지만 **wchar_t** 형식입니다.

에 C++ 표준 라이브러리를 `basic_string` 좁은 문자열과 와이드 문자열에 대 한 특수화 형식입니다. 사용 하 여 `std::string` 형식의 문자 표시 되는 경우 **char**, `std::u16string` 문자 유형의 경우 **char16_t**를 `std::u32string` 문자 형식의 경우 **char32_t** , 및 `std::wstring` 형식의 문자 표시 되는 경우 **wchar_t**합니다. 텍스트를 나타내는 다른 형식 포함 `std::stringstream` 고 `std::cout` 좁은 문자열과 와이드 문자열에 대해 특수화 되었습니다.