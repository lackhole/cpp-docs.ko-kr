---
title: raw_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 23250b524fdaa2181c8e28229ccec680ffdae715
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033257"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes

**C++특정**

세 가지 속성 메서드의 대체 접두사를 지정합니다.

## <a name="syntax"></a>구문

```
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>매개 변수

*GetPrefix*<br/>
에 사용할 접두사를 `propget` 메서드.

*PutPrefix*<br/>
에 사용할 접두사를 `propput` 메서드.

*PutRefPrefix*<br/>
에 사용할 접두사를 `propputref` 메서드.

## <a name="remarks"></a>설명

기본적으로 낮은 수준의 `propget`, `propput`, 및 `propputref` 메서드는 접두사를 사용 하 여 명명 된 멤버 함수에 의해 노출 됩니다 **get_** 를 **put_**, 및 **putref_** 각각. 이 접두사는 MIDL로 생성한 헤더 파일에 사용되는 이름과 호환됩니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)