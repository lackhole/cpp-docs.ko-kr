---
title: raw_property_prefixes import 특성
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: d4d91470781e7c5f673fd228c24904322d1db8b3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216045"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes import 특성

**C++컴퓨터별**

세 가지 속성 메서드의 대체 접두사를 지정합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **raw_property_prefixes (** "*getprefix*" **,** "*putprefix*" **,** "*putrefprefix*" **)**

### <a name="parameters"></a>매개 변수

*GetPrefix*\
`propget` 메서드에 사용할 접두사입니다.

*PutPrefix*\
`propput` 메서드에 사용할 접두사입니다.

*PutRefPrefix*\
`propputref` 메서드에 사용할 접두사입니다.

## <a name="remarks"></a>설명

기본적으로 하위 수준 `propget`, `propput` `propputref` 및 메서드는 각각 `get_`, 및 `putref_`접두사를 `put_`사용 하 여 이라는 멤버 함수에 의해 노출 됩니다. 이 접두사는 MIDL로 생성한 헤더 파일에 사용되는 이름과 호환됩니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
