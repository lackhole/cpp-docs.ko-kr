---
title: retval (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 2a2865c1eda229f1a2fcd457c22119b2908c1caa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514053"
---
# <a name="retval"></a>retval

멤버의 반환 값을 받는 매개 변수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[retval]
```

## <a name="remarks"></a>설명

**Retval** C++ 특성에는 [retval](/windows/win32/Midl/retval) MIDL 특성과 동일한 기능이 있습니다.

**retval** 은 함수 선언의 마지막 인수에 표시 되어야 합니다.

## <a name="example"></a>예제

**Retval**의 샘플 사용에 대 한 [바인딩](bindable.md) 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 매개 변수, 인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|**out**|
|**잘못된 특성**|**in**|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[메서드 특성](method-attributes.md)