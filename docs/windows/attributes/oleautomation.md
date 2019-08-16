---
title: oleautomation (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.oleautomation
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
ms.openlocfilehash: 56970d8b1067e1ac38230b6995074210ddc5549b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514354"
---
# <a name="oleautomation"></a>oleautomation

인터페이스가 자동화와 호환 됨을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[oleautomation]
```

## <a name="remarks"></a>설명

**Oleautomation** C++ 특성은 [oleautomation](/windows/win32/Midl/oleautomation) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

**Oleautomation**의 샘플 사용에 대해서는 [defaultvalue](defaultvalue.md) 및 [비 확장](nonextensible.md) 의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**interface**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|**dispinterface**|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)