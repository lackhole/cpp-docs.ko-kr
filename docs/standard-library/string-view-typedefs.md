---
title: '&lt;string_view&gt; typedef'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 16d7ba49facf24dcffb7df444e445d83d92255e0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346971"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;string_view&gt; typedef

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a> string_view

클래스 템플릿의 특수화를 설명 하는 형식 [basic_string_view](../standard-library/basic-string-view-class.md) 형식의 요소가 포함 된 **char**합니다.

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

## <a name="u16string_view"></a> u16string_view

클래스 템플릿의 특수화를 설명 하는 형식 [basic_string_view](../standard-library/basic-string-view-class.md) 형식의 요소가 있는 `char16_t`합니다.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u32string_view"></a> u32string_view

클래스 템플릿의 특수화를 설명 하는 형식 [basic_string_view](../standard-library/basic-string-view-class.md) 형식의 요소가 있는 `char32_t`합니다.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="wstring_view"></a>  wstring_view

클래스 템플릿의 특수화를 설명 하는 형식 [basic_string_view](../standard-library/basic-string-view-class.md) 형식의 요소가 포함 된 **wchar_t**합니다.

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
> 크기인 **wchar_t** Windows에 2 바이트 이지만 반드시 모든 플랫폼에 대해 대/소문자가 없습니다. String_view 와이드 문자 형식이 필요한 경우 모든 플랫폼에서 동일 하 게 보장 되는 너비를 사용해 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) 하거나 [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)합니다.

## <a name="see-also"></a>참고자료

[\<string_view>](../standard-library/string-view.md)<br/>
