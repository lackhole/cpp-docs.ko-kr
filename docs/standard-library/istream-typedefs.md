---
title: '&lt;istream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: f647fba2036f6c69cb02393e30553c66df34b9dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413296"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; 형식 정의

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

형식 `basic_iostream` 에서 특수화 된 **char**합니다.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_iostream](../standard-library/basic-iostream-class.md)형식의 요소용으로 특수화 된 **char** 기본 문자 특성을 포함 합니다.

## <a name="istream"></a>  istream

형식 `basic_istream` 에서 특수화 된 **char**합니다.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_istream](../standard-library/basic-istream-class.md)형식의 요소용으로 특수화 된 **char** 기본 문자 특성을 포함 합니다.

## <a name="wiostream"></a>  wiostream

형식 `basic_iostream` 에서 특수화 된 **wchar_t**합니다.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_iostream](../standard-library/basic-iostream-class.md)형식의 요소용으로 특수화 된 **wchar_t** 기본 문자 특성을 포함 합니다.

## <a name="wistream"></a>  wistream

형식 `basic_istream` 에서 특수화 된 **wchar_t**합니다.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_istream](../standard-library/basic-istream-class.md)형식의 요소용으로 특수화 된 **wchar_t** 기본 문자 특성을 포함 합니다.

## <a name="see-also"></a>참고자료

[\<istream>](../standard-library/istream.md)<br/>
