---
title: support_error_info (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.support_error_info
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
ms.openlocfilehash: c05b6735c5c29e44f3cc190a150a5efe02025519
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023778"
---
# <a name="supporterrorinfo"></a>support_error_info

자세한 오류 반환에 대한 지원을 구현합니다.

## <a name="syntax"></a>구문

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>매개 변수

*error_interface*<br/>
구현 하는 인터페이스의 식별자 `IErrorInfo`합니다.

## <a name="remarks"></a>설명

**support_error_info** C++ 특성은 대상 개체에서 발생한 자세한 상황별 오류를 클라이언트에 반환하는 작업에 대한 지원을 구현합니다. 오류를의 메서드를 지원 하려면 개체에 대 한는 `IErrorInfo` 개체에서 인터페이스를 구현 해야 합니다. 자세한 내용은 [IDispatch 및 IErrorInfo 지원](../../atl/supporting-idispatch-and-ierrorinfo.md)을 참조하세요.

이 특성은 [ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md) 클래스를 대상 개체에 기본 클래스로 추가합니다. 기본 구현에서는이 인해 `ISupportErrorInfo` 단일 인터페이스가 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다.

## <a name="example"></a>예제

다음 코드에 대 한 기본 지원을 추가 합니다 `ISupportErrorInfo` 인터페이스는 `CMyClass` 개체입니다.

```cpp
// cpp_attr_ref_support_error_info.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="mymod")];
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]
__interface IMyErrors
{
};

[ coclass, support_error_info("IMyErrors"),
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]
class CMyClass
{
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**|
|**반복 가능**|예|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[COM 특성](com-attributes.md)<br/>
[클래스 특성](class-attributes.md)