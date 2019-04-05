---
title: out (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: 7020bd6cfcf8bcdbfb773908e693c6364a29e343
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037583"
---
# <a name="out-c"></a>out(C++)

호출된 프로시저에서 호출하는 프로시저로 반환된(서버에서 클라이언트로 반환된) 포인터 매개 변수를 식별합니다.

## <a name="syntax"></a>구문

```cpp
[out]
```

## <a name="remarks"></a>설명

**out** C++ 특성에는 [out](/windows/desktop/Midl/out-idl) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

[out](bindable.md) 의 샘플 사용에 대해서는 **bindable**에 대한 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 매개 변수|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[ID](id.md)