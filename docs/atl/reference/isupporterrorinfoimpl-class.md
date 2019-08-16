---
title: 은 isupporterrorinfoimpl 클래스
ms.date: 06/13/2019
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: d5e7f087f6646940777ae8b2d2a4ea888fdd3593
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495369"
---
# <a name="isupporterrorinfoimpl-class"></a>은 isupporterrorinfoimpl 클래스

이 클래스는 [ISupportErrorInfo 인터페이스](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) 의 기본 구현을 제공 하며 단일 인터페이스만 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>매개 변수

*piid*<br/>
[IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)를 지 원하는 인터페이스의 IID에 대 한 포인터입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|로 `riid` 식별 되는 인터페이스가 [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스를 지원 하는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

[ISupportErrorInfo 인터페이스](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) 를 사용 하면 오류 정보를 클라이언트에 반환할 수 있습니다. 를 사용 `IErrorInfo` 하는 개체 `ISupportErrorInfo`는를 구현 해야 합니다.

클래스 `ISupportErrorInfoImpl` 는의 `ISupportErrorInfo` 기본 구현을 제공 하며, 단일 인터페이스만 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

로 `riid` 식별 되는 인터페이스가 [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스를 지원 하는지 여부를 나타냅니다.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>설명

Windows SDK에서 [ISupportErrorInfo:: InterfaceSupportsErrorInfo](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
