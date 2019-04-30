---
title: ATL_DRAWINFO 구조체
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: 70329d3b2c18c8cd8e94854f40ff971c0b39a8f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261067"
---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO 구조체

프린터, 메타 파일 또는 ActiveX 컨트롤 같은 다양 한 대상에 렌더링에 사용 되는 정보를 포함 합니다.

## <a name="syntax"></a>구문

```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```

## <a name="members"></a>멤버

`cbSize`<br/>
크기 (바이트)에서 구조입니다.

`dwDrawAspect`<br/>
대상 표시할 방법을 지정 합니다. 콘텐츠, 아이콘, 미리 보기, 또는 인쇄 된 문서 표현이 포함할 수 있습니다. 가능한 값 목록을 참조 하세요 [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) 하 고 [DVASPECT2](/windows/desktop/api/ocidl/ne-ocidl-tagdvaspect2)합니다.

`lindex`<br/>
그리기 작업에 대 한 관심 있는 대상의 부분입니다. 값에 따라 해석이 달라는 `dwDrawAspect` 멤버입니다.

`ptd`<br/>
에 대 한 포인터를 [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) 모양 지정에 따른 그리기 최적화를 사용 하도록 설정 하는 구조입니다. 참고는 최신 개체 및 최적화 된 그리기 인터페이스를 지 원하는 컨테이너 에서도이 멤버를 지원 합니다. 이전 개체 및 컨테이너 항상 최적화 된 그리기 인터페이스 지원 하지 않는이 멤버에 대해 NULL을 지정 합니다.

`hicTargetDev`<br/>
가리키는 대상 장치에 대 한 컨텍스트 정보 `ptd` 개체가 장치 메트릭을 추출 하 고 장치의 기능을 테스트 하는 합니다. 하는 경우 `ptd` 가 null 인 경우 개체의 값을 무시할지를 `hicTargetDev` 멤버입니다.

`hdcDraw`<br/>
그릴 디바이스 컨텍스트입니다. 창 없는 개체에 대 한 합니다 `hdcDraw` 멤버가 `MM_TEXT` 포함 하는 창의 클라이언트 좌표에 일치 하는 논리적 좌표를 사용 하 여 매핑 모드입니다. 장치 컨텍스트를 일반적으로 전달한 것과 동일한 상태 여야 합니다 또한을 `WM_PAINT` 메시지입니다.

`prcBounds`<br/>
에 대 한 포인터를 [RECTL](https://msdn.microsoft.com/library/windows/desktop/dd162907) 에 사각형을 지정 하는 구조 `hdcDraw` 및 개체를 그립니다. 이 멤버는 위치 및 개체의 늘이기를 제어 합니다. 이 멤버에는 창 전체 활성 개체를 그릴 NULL 이어야 합니다. 다른 모든 상황에서 NULL은 올바른 값이 아닙니다 및 개가 수신 되어야는 `E_INVALIDARG` 오류 코드입니다. 창 없는 개체에 NULL이 아닌 값을 전달 하는 컨테이너를 개체는 사각형에 지정 된 디바이스 컨텍스트 요청한 측면을 렌더링 해야 합니다. 컨테이너 개체의 두 번째, 비활성 뷰를 렌더링 하거나 개체를 인쇄 합니다. 창 없는 개체에서이 요청할 수 있습니다.

`prcWBounds`<br/>
하는 경우 `hdcDraw` 메타 파일 장치 컨텍스트는 (참조 [GetDeviceCaps](/windows/desktop/api/wingdi/nf-wingdi-getdevicecaps) Windows SDK에서),이에 대 한 포인터는를 `RECTL` 내부 메타 파일의 경계 사각형을 지정 하는 구조입니다. 창 크기와 창 원본 사각형 구조에 포함 되어 있습니다. 이러한 값은 메타 파일 그리기에 유용 합니다. 사각형에 나타난 `prcBounds` 이 중첩 `prcWBounds` 사각형의 동일한 좌표 공간에서.

`bOptimize`<br/>
컨트롤의 그리기를 최적화 하 고 그렇지 않은 0 이면 0이 아닙니다. 완료 했으면 장치 컨텍스트의 상태는 자동으로 복원 그리기를 최적화 하는 경우 렌더링 합니다.

`bZoomed`<br/>
이 속성을 0이 아닌 대상에 확대/축소 비율, 그렇지 않으면 0입니다. 확대/축소 비율에 저장 된 `ZoomNum`합니다.

`bRectInHimetric`<br/>
0이 아닌 값의 크기 `prcBounds` HIMETRIC, 그렇지 않으면 0에 있습니다.

`ZoomNum`<br/>
개체 렌더링 되는 사각형의 높이 너비입니다. X 축의 (현재 범위에 해당 개체의 기본 크기의 비율) 대상의 확대/축소 비율의 값인 `ZoomNum.cx` 의 값으로 나눈 `ZoomDen.cx`합니다. Y 축의 확대/축소 비율을 비슷한 방식으로 이루어집니다.

`ZoomDen`<br/>
실제 너비와 높이의 대상입니다.

## <a name="remarks"></a>설명

이 구조체의 일반적인 사용 대상 개체의 렌더링 하는 동안 정보를 검색할 수 있습니다. 에 오버 로드 내에서 ATL_DRAWINFO 값을 검색할 수는 예를 들어 [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)합니다.

이 구조는 대상 장치에 대 한 개체의 모양을 렌더링 하는 데 사용 되는 관련 정보를 저장 합니다. 제공 된 정보는 화면, 프린터 또는 메타 파일 그리기에 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="see-also"></a>참고자료

[클래스 및 구조체](../../atl/reference/atl-classes.md)<br/>
[IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)
