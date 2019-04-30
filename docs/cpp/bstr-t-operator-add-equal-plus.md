---
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: 0a2c374fc160a0575e0a17cc85ab51c65fa9392a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390835"
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +

**Microsoft 전용**

`_bstr_t` 개체의 끝에 문자를 추가하거나 두 문자열을 연결합니다.

## <a name="syntax"></a>구문

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>매개 변수

*s1*<br/>
`_bstr_t` 개체입니다.

*s2*<br/>
멀티바이트 문자열입니다.

*s3*<br/>
유니코드 문자열입니다.

## <a name="remarks"></a>설명

이러한 연산자는 다음과 같이 문자열 연결을 수행합니다.

- **operator + = (***s1***)** 캡슐화 된 문자를 추가 `BSTR` 의 *s1* 캡슐화 가이개체의끝에`BSTR`.

- **operator + (***s1***)** 새 반환 `_bstr_t` 이 개체를 연결 하 여 형성 된 `BSTR` 의 지 문으로 *s1*합니다.

- **operator + (***s2***&#124;***s1***)** 새 반환 `_bstr_t` 연결 하 여 형성 된를 멀티 바이트 문자열 *s2*유니코드로 변환 된와 `BSTR` 캡슐화 *s1*합니다.

- **operator + (***s3* **하십시오***s1***)** 반환 된 새 `_bstr_t` 유니코드 문자열을 연결 하 여 형성 된 *s3* 사용 하 여 합니다 `BSTR` 캡슐화 *s1*합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)