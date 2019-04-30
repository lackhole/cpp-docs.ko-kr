---
title: '&lt;streambuf&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 505739861771a05dd39741f432579a6e9b2d0c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412386"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; 형식 정의

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

특수화 `basic_streambuf` 를 사용 하는 **char** 템플릿 매개 변수로 합니다.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_streambuf](../standard-library/basic-streambuf-class.md)형식의 요소용으로 특수화 된 **char** 기본 문자 특성을 포함 합니다.

## <a name="wstreambuf"></a>  wstreambuf

특수화 `basic_streambuf` 를 사용 하는 **wchar_t** 템플릿 매개 변수로 합니다.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_streambuf](../standard-library/basic-streambuf-class.md)형식의 요소용으로 특수화 된 **wchar_t** 기본 문자 특성을 포함 합니다.

## <a name="see-also"></a>참고자료

[\<streambuf>](../standard-library/streambuf.md)<br/>
