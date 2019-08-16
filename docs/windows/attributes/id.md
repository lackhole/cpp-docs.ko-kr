---
title: id (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 6f1d1d2b9d147e8b33b3b5fae629e0805971bb71
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501414"
---
# <a name="id"></a>id

인터페이스 또는 인터페이스에서 멤버 함수 (속성 또는 메서드)에 대 한 *dispid* 매개 변수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
인터페이스 메서드의 디스패치 ID입니다.

## <a name="remarks"></a>설명

**Id** C++ 특성에는 [id](/windows/win32/Midl/id) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**Id**를 사용 하는 방법에 대 한 예제는 [바인딩](bindable.md) 가능의 예제를 참조 하세요.

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
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)