---
title: '&lt;string_view&gt; typedef'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: c3367afe1353ac70abb74a59658a255614ac8470
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459177"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;string_view&gt; typedef

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a>string_view

**Char**형식의 요소가 있는 클래스 템플릿 [basic_string_view](../standard-library/basic-string-view-class.md) 의 특수화를 설명 하는 형식입니다.

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u16string_view"></a>u16string_view

형식의`char16_t`요소를 포함 하는 클래스 템플릿 [basic_string_view](../standard-library/basic-string-view-class.md) 의 특수화를 설명 하는 형식입니다.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u32string_view"></a>u32string_view

형식의`char32_t`요소를 포함 하는 클래스 템플릿 [basic_string_view](../standard-library/basic-string-view-class.md) 의 특수화를 설명 하는 형식입니다.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="wstring_view"></a>  wstring_view

**Wchar_t**형식의 요소가 있는 클래스 템플릿 [basic_string_view](../standard-library/basic-string-view-class.md) 의 특수화를 설명 하는 형식입니다.

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

> [!NOTE]
> **Wchar_t** 의 크기는 Windows에서 2 바이트 이지만 모든 플랫폼의 경우는 아닙니다. 모든 플랫폼에서 너비가 동일 하 게 유지 되도록 보장 되는 string_view 와이드 문자 형식이 필요한 경우 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) 또는 [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)를 사용 합니다.

## <a name="see-also"></a>참고자료

[\<string_view>](../standard-library/string-view.md)
