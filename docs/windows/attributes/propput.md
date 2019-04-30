---
title: propput (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: c9853b38675abfa0a94a319ac752eb2ef61a48e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407525"
---
# <a name="propput"></a>propput

속성 설정 함수를 지정합니다.

## <a name="syntax"></a>구문

```cpp
[propput]
```

## <a name="remarks"></a>설명

**propput** C++ 특성에 동일한 기능을 합니다 [propput](/windows/desktop/Midl/propput) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [bindable](bindable.md) 의 샘플 사용에 대 한 **propput**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|`propget`, `propputref`|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)