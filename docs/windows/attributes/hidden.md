---
title: 숨겨진 (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: d1d87ea057b22984a0e0f8f5518899e36f7d0221
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409514"
---
# <a name="hidden"></a>hidden

항목이 있지만 하지 사용자 기반 브라우저에 표시할지를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[hidden]
```

## <a name="remarks"></a>설명

**숨겨진** C++ 특성에 동일한 기능을 합니다 [숨겨진](/windows/desktop/Midl/hidden) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [바인딩 가능한](bindable.md) 사용 하는 방법의 예제 **숨겨진**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**인터페이스**하십시오 **클래스**합니다 **구조체**, 메서드, 속성|
|**반복 가능**|아니요|
|**필수 특성**|**coclass** (적용할 때 **클래스** 하거나 **구조체**)|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[메서드 특성](method-attributes.md)