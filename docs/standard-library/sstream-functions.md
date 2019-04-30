---
title: '&lt;sstream&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: f22aec854b9a1d9b7b8360cacbb08760413fa22e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412516"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 함수

||
|-|
|[swap](#sstream_swap)|

## <a name="sstream_swap"></a>  swap

두 `sstream` 개체 간에 값을 교환합니다.

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*left*|`sstream` 개체에 대한 참조입니다.|
|*right*|`sstream` 개체에 대한 참조입니다.|

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`을 실행합니다.

## <a name="see-also"></a>참고자료

[\<sstream>](../standard-library/sstream.md)<br/>
