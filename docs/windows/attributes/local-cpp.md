---
title: 로컬 (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 678968bb7b0f2e7af94124bea5b0967df27e43f7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033072"
---
# <a name="local-c"></a>local(C++)

인터페이스 헤더를 사용할 경우 MIDL 컴파일러 헤더 생성기로 사용할 수 있습니다. 개별 함수를 사용할 경우 없는 스텁 생성 되는 로컬 프로시저를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[local]
```

## <a name="remarks"></a>설명

합니다 **로컬** c + + 특성에 동일한 기능을 합니다 [로컬](/windows/desktop/Midl/local) MIDL 특성입니다.

## <a name="example"></a>예제

참조 [call_as](call-as.md) 사용 하는 방법의 예제 **로컬**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**인터페이스**, 인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|`dispinterface`|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[call_as](call-as.md)