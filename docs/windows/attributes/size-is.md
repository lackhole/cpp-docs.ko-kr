---
title: size_is (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: a7b990a708bafba78c9dc4153315f8b7b20351ba
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033232"
---
# <a name="sizeis"></a>size_is

메모리 크기의 할당 크기의 포인터에 대 한 크기의 포인터 및 단일 또는 다차원 배열에 대 한 포인터 크기 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>매개 변수

*expression*<br/>
크기가 지정 된 포인터에 할당 된 메모리의 크기입니다.

## <a name="remarks"></a>설명

합니다 **size_is** c + + 특성에 동일한 기능을 합니다 [size_is](/windows/desktop/Midl/size-is) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [first_is](first-is.md) 배열 섹션을 지정 하는 방법의 예제입니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|필드에 **구조체** 하거나 **union**인터페이스 매개 변수, 인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|`max_is`|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)