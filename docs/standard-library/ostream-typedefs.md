---
title: '&lt;ostream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 18f30a12a6f4d2b97cb5dca3ace98e6241d856a7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447173"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; 형식 정의

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Char에서 특수 **하 고** `char_traits` **char**에서 특수화 된 basic_ostream에서 형식을 만듭니다.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 [basic_ostream](../standard-library/basic-ostream-class.md)템플릿 클래스의 동의어입니다.

## <a name="wostream"></a>  wostream

Wchar_t에서 특수화 **되 고** `char_traits` **wchar_t**에서 특수화 된 basic_ostream에서 형식을 만듭니다.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **wchar_t** 형식의 요소에 대해 특수화 된 [basic_ostream](../standard-library/basic-ostream-class.md)템플릿 클래스의 동의어입니다.

## <a name="see-also"></a>참고자료

[\<ostream>](../standard-library/ostream.md)
