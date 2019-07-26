---
title: '&lt;istream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 864854fa2697a76c2f3476bcb050d5f5d084dc9d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458756"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; 형식 정의

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

Char에서 `basic_iostream` 특수화 된 형식입니다.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 [basic_iostream](../standard-library/basic-iostream-class.md)템플릿 클래스의 동의어입니다.

## <a name="istream"></a>  istream

Char에서 `basic_istream` 특수화 된 형식입니다.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 [basic_istream](../standard-library/basic-istream-class.md)템플릿 클래스의 동의어입니다.

## <a name="wiostream"></a>  wiostream

Wchar_t에서 `basic_iostream` 특수화 된 형식입니다.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **wchar_t** 형식의 요소에 대해 특수화 된 [basic_iostream](../standard-library/basic-iostream-class.md)템플릿 클래스의 동의어입니다.

## <a name="wistream"></a>  wistream

Wchar_t에서 `basic_istream` 특수화 된 형식입니다.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **wchar_t** 형식의 요소에 대해 특수화 된 [basic_istream](../standard-library/basic-istream-class.md)템플릿 클래스의 동의어입니다.

## <a name="see-also"></a>참고자료

[\<istream>](../standard-library/istream.md)
