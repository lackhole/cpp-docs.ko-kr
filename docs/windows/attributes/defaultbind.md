---
title: defaultbind (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultbind
helpviewer_keywords:
- defaultbind attribute
ms.assetid: b20a8437-24e6-4b6d-a2df-09fe5e1006e0
ms.openlocfilehash: a2f612c4869a62a84a6a2af99057ced365f875f2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490985"
---
# <a name="defaultbind"></a>defaultbind

개체를 가장 잘 나타내는 바인딩 가능한 단일 속성을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[defaultbind]
```

## <a name="remarks"></a>설명

**Defaultbind** C++ 특성에는 [defaultbind](/windows/win32/Midl/defaultbind) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**Defaultbind**를 사용 하는 방법에 대 한 예제는 [바인딩](bindable.md) 가능의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[데이터 멤버 특성](data-member-attributes.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)