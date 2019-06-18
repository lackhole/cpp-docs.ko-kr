---
title: ISupportErrorInfoImpl 클래스
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
ms.openlocfilehash: 650d90c9ec98754e11586f63e0871b70ebbe34f3
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141699"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl 클래스

이 클래스의 기본 구현을 제공 합니다 [ISupportErrorInfo 인터페이스](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) 는 단일 인터페이스만 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다.

> [!IMPORTANT]
> 이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>매개 변수

*piid*<br/>
지 원하는 인터페이스의 IID에 대 한 포인터 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|인터페이스를 구분 하는지 여부를 나타냅니다 `riid` 지원 합니다 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스입니다.|

## <a name="remarks"></a>설명

합니다 [ISupportErrorInfo 인터페이스](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) 하면 클라이언트에 오류 정보를 반환할 수 있습니다. 사용 하는 개체 `IErrorInfo` 구현 해야 `ISupportErrorInfo`합니다.

클래스 `ISupportErrorInfoImpl` 의 기본 구현을 제공 `ISupportErrorInfo` 는 단일 인터페이스만 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

인터페이스를 구분 하는지 여부를 나타냅니다 `riid` 지원 합니다 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스입니다.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>설명

참조 [ISupportErrorInfo::InterfaceSupportsErrorInfo](/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
