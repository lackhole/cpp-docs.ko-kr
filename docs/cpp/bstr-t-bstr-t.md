---
title: _bstr_t::_bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
ms.openlocfilehash: 44a301b8b2a1c53636c27be6f59f61aa0dcd46b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385013"
---
# <a name="bstrtbstrt"></a>_bstr_t::_bstr_t

**Microsoft 전용**

`_bstr_t` 개체를 생성합니다.

## <a name="syntax"></a>구문

```
_bstr_t( ) throw( );
_bstr_t(
   const _bstr_t& s1
) throw( );
_bstr_t(
   const char* s2
);
_bstr_t(
   const wchar_t* s3
);
_bstr_t(
   const _variant_t& var
);
_bstr_t(
   BSTR bstr,
   bool fCopy
);
```

#### <a name="parameters"></a>매개 변수

*s1*<br/>
복사할 `_bstr_t` 개체입니다.

*s2*<br/>
멀티바이트 문자열입니다.

*s3*<br/>
유니코드 문자열입니다.

*var*<br/>
A [_variant_t](../cpp/variant-t-class.md) 개체입니다.

*bstr*<br/>
기존 `BSTR` 개체입니다.

*fCopy*<br/>
FALSE 이면 합니다 *bstr* 인수를 호출 하 여 복사본을 만들지 않고 새 개체에 연결 된 `SysAllocString`합니다.

## <a name="remarks"></a>설명

다음 표는 `_bstr_t` 생성자에 대해 설명합니다.

|생성자|설명|
|-----------------|-----------------|
|`_bstr_t( )`|기본값을 생성 `_bstr_t` null을 캡슐화 하는 개체 `BSTR` 개체입니다.|
|`_bstr_t( _bstr_t&`  `s1`  `)`|`_bstr_t` 개체를 다른 개체의 복사본으로 생성합니다.<br /><br /> 이 *단순* 캡슐화 된의 참조 횟수를 증가 시키는 복사 `BSTR` 새로 만드는 대신 개체입니다.|
|`_bstr_t( char*`  `s2`  `)`|새 `_bstr_t` 개체를 만드는 `SysAllocString`을 호출하여 `BSTR` 개체를 생성한 다음 캡슐화합니다.<br /><br /> 이 생성자는 먼저 멀티바이트를 유니코드로 변환합니다.|
|`_bstr_t( wchar_t*`  `s3`  `)`|새 `_bstr_t` 개체를 만드는 `SysAllocString`을 호출하여 `BSTR` 개체를 생성한 다음 캡슐화합니다.|
|`_bstr_t( _variant_t&`  `var`  `)`|캡슐화된 VARIANT 개체에서 `_bstr_t` 개체를 먼저 검색하여 `_variant_t` 개체에서 `BSTR` 개체를 생성합니다.|
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|기존 `_bstr_t`(`BSTR` 문자열의 반대)에서 `wchar_t*` 개체를 생성합니다. 하는 경우 *fCopy* 이 false 인 경우 제공 된 `BSTR` 사용 하 여 새 복사본을 만들지 않고 새 개체에 연결 된 `SysAllocString`합니다.<br /><br /> 이 생성자는 형식 라이브러리 헤더의 래퍼 함수에서 사용되어 인터페이스 메서드에서 반환하는 `BSTR`을 캡슐화하고 그 소유권을 가집니다.|

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)<br/>
[_variant_t 클래스](../cpp/variant-t-class.md)