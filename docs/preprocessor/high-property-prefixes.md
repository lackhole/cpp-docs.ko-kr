---
title: high_property_prefixes import 특성
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 9e44f6f1afae479f803f4c6d866ef3ee38744561
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219006"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes import 특성

**C++컴퓨터별**

세 가지 속성 메서드의 대체 접두사를 지정합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **high_property_prefixes (** "*getprefix*" **,** "*putprefix*" **,** "*putrefprefix*" **)**

### <a name="parameters"></a>매개 변수

*GetPrefix*\
`propget` 메서드에 사용할 접두사입니다.

*PutPrefix*\
`propput` 메서드에 사용할 접두사입니다.

*PutRefPrefix*\
`propputref` 메서드에 사용할 접두사입니다.

## <a name="remarks"></a>설명

기본적으로 상위 수준 오류 처리 `propget`, `propput`및 `propputref` 메서드는 각각 접두사 `Get`, `Put`및 `PutRef`로 명명 된 멤버 함수에 의해 노출 됩니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
