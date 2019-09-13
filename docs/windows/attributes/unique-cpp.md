---
title: unique (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.unique
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
ms.openlocfilehash: 91e563ed121ba09e0c2ca2660f30c75956232ea0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514905"
---
# <a name="unique-c"></a>unique(C++)

고유 포인터를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[unique]
```

## <a name="remarks"></a>설명

**Unique** C++ 특성에는 [고유한](/windows/win32/Midl/unique) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**고유한**의 샘플 [사용에 대 한 참조 예제를](ref-cpp.md) 참조 하십시오.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**typedef**, **struct**, **union**, interface parameter, interface 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)