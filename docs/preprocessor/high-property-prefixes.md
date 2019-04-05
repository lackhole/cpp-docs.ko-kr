---
title: high_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 3f8975ec9737e02bb1216166cc6c241549e95a07
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029371"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes

**C++ 전용**

세 가지 속성 메서드의 대체 접두사를 지정합니다.

## <a name="syntax"></a>구문

```
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>매개 변수

*GetPrefix*<br/>
에 사용할 접두사를 `propget` 메서드.

*PutPrefix*<br/>
에 사용할 접두사를 `propput` 메서드.

*PutRefPrefix*<br/>
에 사용할 접두사를 `propputref` 메서드.

## <a name="remarks"></a>설명

기본적으로 상위 수준 오류 처리 `propget`, `propput`, 및 `propputref` 메서드는 접두사로 명명 된 멤버 함수에 의해 노출 됩니다 `Get`를 `Put`, 및 `PutRef`각각.

**C++ 전용 종료**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)