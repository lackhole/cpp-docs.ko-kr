---
title: '&lt;ostream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 02936fdfc990ea65a99b2875cf7f482eb2ce4ebe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370881"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; 형식 정의

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

특수화 된 basic_ostream에서 유형을 만듭니다 **char** 하 고 `char_traits` 에서 특수화 된 **char**합니다.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_ostream](../standard-library/basic-ostream-class.md)형식의 요소용으로 특수화 된 **char** 기본 문자 특성을 포함 합니다.

## <a name="wostream"></a>  wostream

특수화 된 basic_ostream에서 유형을 만듭니다 **wchar_t** 하 고 `char_traits` 에서 특수화 된 **wchar_t**합니다.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_ostream](../standard-library/basic-ostream-class.md)형식의 요소용으로 특수화 된 **wchar_t** 기본 문자 특성을 포함 합니다.

## <a name="see-also"></a>참고자료

[\<ostream>](../standard-library/ostream.md)<br/>
