---
title: IAxWinAmbientDispatchEx 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: 638152d8c49bd20742a586bc665efcdb662b6f3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276096"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx 인터페이스

이 인터페이스는 호스트 된 컨트롤에 대 한 보조 앰비언트 속성을 구현합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|이 메서드는 사용자 정의 인터페이스를 사용 하 여 기본 앰비언트 속성 인터페이스를 보완 하기 위해 호출 됩니다.|

## <a name="remarks"></a>설명

ATL 및 호스트 ActiveX 컨트롤, 특히 앰비언트 속성을 갖는 ActiveX 컨트롤에 정적으로 연결 된 ATL 응용 프로그램에이 인터페이스를 포함 합니다. 이 인터페이스를 포함 하지 않고이 어설션이 생성 됩니다. "했는지 LIBID CComModule::Init 전달할"

이 인터페이스는 개체를 호스트 하는 ATL의 ActiveX 컨트롤에 의해 노출 됩니다. 파생 된 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` 자신만의 하나를 사용 하 여 ATL 제공한 앰비언트 속성 인터페이스를 보완할 수 있습니다 하는 메서드를 추가 합니다.

<xref:System.Windows.Forms.AxHost> 에 대 한 형식 정보를 로드 하려고 `IAxWinAmbientDispatch` 고 `IAxWinAmbientDispatchEx` 코드가 포함 된 형식 라이브러리에서.

ATL90.dll를 연결할 경우 **AXHost** DLL의 형식 라이브러리에서 형식 정보를 로드 합니다.

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 대 한 자세한 내용은 합니다.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의 다음 표에 나와 있는 것 처럼 다양 한 폼에서에서 사용할 수 있습니다.

|정의 유형|파일|
|---------------------|----------|
|IDL|atliface.idl|
|형식 라이브러리|ATL.dll|
|C++|atliface.h (ATLBase.h에도 포함)|

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

이 메서드는 사용자 정의 인터페이스를 사용 하 여 기본 앰비언트 속성 인터페이스를 보완 하기 위해 호출 됩니다.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>매개 변수

*pDispatch*<br/>
새 인터페이스에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

때 `SetAmbientDispatch` 호출 되는 새 인터페이스에 대 한 포인터를 사용 하 여이 새 인터페이스 하는 데 사용할 속성 또는 해당 속성에서 이미 제공 하지 않는 경우 호스트 된 컨트롤에 의해 요청 메서드를 호출 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>참고자료

[IAxWinAmbientDispatch 인터페이스](../../atl/reference/iaxwinambientdispatch-interface.md)
