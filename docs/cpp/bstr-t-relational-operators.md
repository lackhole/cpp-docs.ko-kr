---
title: _bstr_t 관계형 연산자
ms.date: 05/07/2019
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
helpviewer_keywords:
- _bstr_t [C++]
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
ms.openlocfilehash: 57a9379be6d90cfb574ea0dcc033692762c47990
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222238"
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