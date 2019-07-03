---
title: IDocHostUIHandlerDispatch 인터페이스
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: a60c178eff1e02c3032e792f9a0420dfeab82388
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552164"
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch 인터페이스

인터페이스는 Microsoft HTML 구문 분석 및 렌더링 엔진입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

> [!NOTE]
>  멤버에 대 한 INet SDK 참조 항목에는 다음 표의 링크를 클릭 합니다 [IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) 인터페이스입니다. `IDocHostUIHandlerDispatch` 동일한 기능이 `IDocUIHostHandler`는 차이점 `IDocHostUIHandlerDispatch` 는 dispinterface는 반면 `IDocUIHostHandler` 사용자 지정 인터페이스입니다.

|||
|-|-|
|[EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|MSHTML 구현에서 호출 [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)합니다. MSHTML 모달 UI를 표시 하는 경우 라고도 합니다.|
|[FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|호스트 MSHTML의 데이터 개체를 바꿀 수 있도록 MSHTML에 의해 호스트에서 호출 됩니다.|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|대안을 제공 하는 호스트 수 있도록 놓기 대상으로 사용 되는 경우 MSHTML 호출한 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget)합니다.|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|호스트의 IDispatch 인터페이스를 가져올 MSHTML에 의해 호출 됩니다.|
|[GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|MSHTML 호스트의 UI 기능을 검색합니다.|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|MSHTML는 사용자 기본 설정을 저장 하는 레지스트리 키를 반환 합니다.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|해당 메뉴 및 도구 모음 MSHTML 제거 하는 경우 호출 됩니다.|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|MSHTML 구현에서 호출 [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate)합니다.|
|[OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|MSHTML 구현에서 호출 [ioleinplaceactiveobject:: Onframewindowactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate)합니다.|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|MSHTML 구현에서 호출 [IOleInPlaceActiveObject::ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder)합니다.|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|상황에 맞는 메뉴를 표시할 MSHTML에서 호출 됩니다.|
|[ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|호스트를 MSHTML 메뉴 및 도구 모음을 교체할 수 있습니다.|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|MSHTML에 의해 호출 하면 [ioleinplaceactiveobject:: Translateaccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) 하거나 [iolecontrolsite:: Translateaccelerator](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) 라고 합니다.|
|[TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|호스트가 로드할 URL을 수정할 수 있도록 MSHTML에 의해 호출 됩니다.|
|[UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|명령 상태가 변경되었음을 호스트에 알립니다.|

## <a name="remarks"></a>설명

호스트 메뉴, 도구 모음 및이 인터페이스를 구현 하 여 Microsoft HTML 구문 분석 및 렌더링 엔진 (MSHTML) 사용 하는 상황에 맞는 메뉴를 바꿀 수 있습니다.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의 IDL로 제공 됩니다. 또는 C++다음과 같이 합니다.

|정의 유형|파일|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|ATLIFace.h (ATLBase.h에도 포함)|

## <a name="see-also"></a>참고자료

[IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
