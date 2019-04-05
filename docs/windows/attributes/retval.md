---
title: retval (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 9f5ad86a289f8904278a58636e66809ae0edd55b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035101"
---
# <a name="retval"></a>retval

멤버의 반환 값을 받는 매개 변수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[retval]
```

## <a name="remarks"></a>설명

합니다 **retval** c + + 특성에 동일한 기능을 합니다 [retval](/windows/desktop/Midl/retval) MIDL 특성입니다.

**retval** 함수 선언에서 마지막 인수에 표시 되어야 합니다.

## <a name="example"></a>예제

예를 참조 하세요 [bindable](bindable.md) 의 샘플 사용에 대 한 **retval**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 매개 변수를 인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|**out**|
|**잘못된 특성**|**의**|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[메서드 특성](method-attributes.md)