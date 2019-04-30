---
title: _bstr_t 관계형 연산자
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- operator<= [C++], bstr
- '!= operator'
- operator == [C++], bstr
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- relational operators [C++], _bstr_t class
- operator== [C++], bstr
- <= operator [C++], with specific objects
- operator <= [C++], bstr
- operator >= [C++], bstr
- operator != [C++], relational operators
- '> operator [C++], comparing specific objects'
- operator< [C++], bstr
- == operator [C++], with specific Visual C++ objects
- operator>= [C++], bstr
- operator < [C++], bstr
- operator > [C++], bstr
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
ms.openlocfilehash: f454c8bcfeb28ada8c07564e9bb562e18a537e45
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345166"
---
# <a name="bstrt-relational-operators"></a>_bstr_t 관계형 연산자

**Microsoft 전용**

두 `_bstr_t` 개체를 비교합니다.

## <a name="syntax"></a>구문

```
bool operator!( ) const throw( );
bool operator==(const _bstr_t& str) const throw( );
bool operator!=(const _bstr_t& str) const throw( );
bool operator<(const _bstr_t& str) const throw( );
bool operator>(const _bstr_t& str) const throw( );
bool operator<=(const _bstr_t& str) const throw( );
bool operator>=(const _bstr_t& str) const throw( );
```

## <a name="remarks"></a>설명

이러한 연산자는 두 `_bstr_t` 개체를 사전순으로 비교합니다. TRUE를 반환 하는 연산자는 비교가 유효 하면 그렇지 않으면 FALSE를 반환 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)