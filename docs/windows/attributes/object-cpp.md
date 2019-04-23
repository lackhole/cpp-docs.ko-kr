---
title: 개체 (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: c0f544e84e5110761dfd01e25abef4352f055ff5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022361"
---
# <a name="object-c"></a>object(C++)

사용자 지정 인터페이스를 식별합니다.

## <a name="syntax"></a>구문

```cpp
[object]
```

## <a name="remarks"></a>설명

인터페이스 정의 이전 하는 경우는 **개체** C++ 특성을 사용 하면 사용자 지정 인터페이스.idl 파일에 배치 하는 인터페이스입니다.

개체를 사용 하 여 표시 된 모든 인터페이스에서 상속 해야 `IUnknown`합니다. 기본 인터페이스에서 상속 하는 경우이 조건이 만족 `IUnknown`합니다. 상속 된 기본 인터페이스가 없는 경우 `IUnknown`, 컴파일러에 표시 된 인터페이스 하면 **개체** 에서 파생 `IUnknown`합니다.

## <a name="example"></a>예제

참조 [nonbrowsable](nonbrowsable.md) 사용 하는 방법의 예제 **개체**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**interface**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)