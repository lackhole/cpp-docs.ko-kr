---
title: implements_category (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.implements_category
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
ms.openlocfilehash: bbd859018210d3c972ae9d4b0e9f659d96d95aab
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504193"
---
# <a name="implementscategory"></a>implements_category

대상 클래스에서 구현 되는 구성 요소 범주를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>매개 변수

*implements_category*<br/>
구현 된 범주의 ID입니다.

## <a name="remarks"></a>설명

합니다 **implements_category** C++ 특성 대상 클래스에 의해 구현 된 구성 요소 범주를 지정 합니다. 범주 지도 만들고 지정 된 별도 항목을 추가 하 여 이렇게 합니다 **implements_category** 특성입니다. 자세한 내용은 [구성 요소 범주 and How They](/windows/desktop/com/component-categories-and-how-they-work)합니다.

이 특성을 사용하려면 [coclass](coclass.md), [progid](progid.md)또는 [vi_progid](vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 있으면 `progid` 적용 됩니다 `vi_progid` 및 `coclass` 도 적용 됩니다.

## <a name="example"></a>예제

다음 코드를 다음 구현 된 개체가 지정 된 `Control` 범주입니다.

```cpp
// cpp_attr_ref_implements_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLib")];
[ coclass, implements_category("CATID_Control"),
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]
class CMyClass {};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|예|
|**필수 특성**|다음 중 하나: `coclass`, `progid`, 또는 `vi_progid`|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[COM 특성](com-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)