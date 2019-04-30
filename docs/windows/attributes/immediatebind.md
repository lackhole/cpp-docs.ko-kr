---
title: immediatebind (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.immediatebind
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
ms.openlocfilehash: 1844e72ecd1fe7c0f4255426eb48f5c70471e5f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409475"
---
# <a name="immediatebind"></a>immediatebind

데이터베이스는 즉시 알림을 받을 수는 데이터 바인딩된 개체의 속성에는 모든 변경 내용을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[immediatebind]
```

## <a name="remarks"></a>설명

**immediatebind** C++ 특성에 동일한 기능을 합니다 [immediatebind](/windows/desktop/Midl/immediatebind) MIDL 특성입니다.

## <a name="example"></a>예제

참조 [bindable](bindable.md) 사용 하는 방법의 예 **immediatebind**합니다.

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
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[requestedit](requestedit.md)