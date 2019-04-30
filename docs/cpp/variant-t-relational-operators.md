---
title: _variant_t 관계형 연산자
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: e0d26247868440f47c73422510ac0e998f8e8dee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403297"
---
# <a name="variantt-relational-operators"></a>_variant_t 관계형 연산자

**Microsoft 전용**

두 `_variant_t` 개체가 같음 또는 같지 않음을 비교합니다.

## <a name="syntax"></a>구문

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>매개 변수

*varSrc*<br/>
A `VARIANT` 와 비교 되는 `_variant_t` 개체입니다.

*pSrc*<br/>
에 대 한 포인터를 `VARIANT` 와 비교 되는 `_variant_t` 개체입니다.

## <a name="return-value"></a>반환 값

반환 **true** 비교를 보유 하는 경우 **false** 그렇지 않은 경우.

## <a name="remarks"></a>설명

비교는 `_variant_t` 개체는 `VARIANT`, 같음 또는 같지 않음을 테스트 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_variant_t 클래스](../cpp/variant-t-class.md)