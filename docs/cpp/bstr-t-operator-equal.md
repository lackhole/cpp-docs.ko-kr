---
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 97f0100d8a34253f3a1375d34b887d3d31a77f43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350873"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =

**Microsoft 전용**

기존 `_bstr_t` 개체에 새 값을 할당합니다.

## <a name="syntax"></a>구문

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>매개 변수

*s1*<br/>
기존 `_bstr_t` 개체에 할당될 `_bstr_t` 개체입니다.

*s2*<br/>
기존 `_bstr_t` 개체에 할당될 멀티바이트 문자열입니다.

*s3*<br/>
기존 `_bstr_t` 개체에 할당될 유니코드 문자열입니다.

*var*<br/>
기존 `_variant_t` 개체에 할당될 `_bstr_t` 개체입니다.

**Microsoft 전용 종료**

## <a name="example"></a>예제

참조 [_bstr_t:: assign](../cpp/bstr-t-assign.md) 사용 하는 예제에 대 한 **연산자 =** 합니다.

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)