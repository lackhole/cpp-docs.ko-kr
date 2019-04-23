---
title: CMFCLinkCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: 839448694cee17f5bc1a1e47f7c113026a1a4006
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776429"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl 클래스

`CMFCLinkCtrl` 클래스 하이퍼링크 단추를 표시 하 고 단추를 클릭할 때 링크 대상을 호출 합니다.

## <a name="syntax"></a>구문

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCLinkCtrl::SetURL](#seturl)|단추 텍스트와 지정 된 URL을 표시합니다.|
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|암시적 프로토콜을 설정 합니다 (예를 들어, "http:")의 URL입니다.|
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|단추 텍스트나 비트맵 단추의 크기를 조정 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|포커스 사각형에서 단추를 그리기 전에 프레임 워크에서 호출 됩니다.|

## <a name="remarks"></a>설명

파생 되는 단추를 클릭할 때 합니다 `CMFCLinkCtrl` 클래스를 프레임 워크는 매개 변수로 단추의 URL을 전달 합니다 `ShellExecute` 메서드. 그런 다음 `ShellExecute` 메서드 url 대상을 엽니다.

## <a name="example"></a>예제

다음 예제에서는 크기를 설정 하는 방법에 설명 된 `CMFCLinkCtrl` 개체 및 설정 url 및 도구를 설명 하는 방법을 `CMFCLinkCtrl` 개체입니다. 이 예제는의 일부를 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxlinkctrl.h

##  <a name="ondrawfocusrect"></a>  CMFCLinkCtrl::OnDrawFocusRect

포커스 사각형에서 단추를 그리기 전에 프레임 워크에서 호출 됩니다.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rectClient*<br/>
[in] 링크 컨트롤을 제한 하는 사각형입니다.

### <a name="remarks"></a>설명

단추의 포커스 사각형을 그릴 사용자 고유의 코드를 사용 하려는 경우이 메서드를 재정의 합니다.

##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL

단추 텍스트와 지정 된 URL을 표시합니다.

```
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
[in] 단추 텍스트 표시입니다.

### <a name="remarks"></a>설명

##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix

암시적 프로토콜을 설정 합니다 (예를 들어, "http:")의 URL입니다.

```
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>매개 변수

*lpszPrefix*<br/>
[in] URL 프로토콜의 접두사입니다.

### <a name="remarks"></a>설명

URL 접두사를 설정 하려면이 메서드를 사용 합니다. 접두사 단추의 얼굴에 표시 되지 않지만 URL의 대상으로 이동 하는 데 사용할 수 있습니다.

##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent

단추 텍스트나 비트맵 단추의 크기를 조정 합니다.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>매개 변수

*bVCenter*<br/>
[in] 단추 텍스트 및 비트맵 위쪽과 아래쪽 링크 컨트롤 간에 세로로 가운데 TRUE 그렇지 않으면 FALSE입니다. 기본값은 FALSE입니다.

*bHCenter*<br/>
[in] 단추 텍스트 및 링크 컨트롤의 왼쪽과 오른쪽 간 가로 방향으로 비트맵 가운데 TRUE 그렇지 않으면 FALSE입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>반환 값

A [CSize](../../atl-mfc-shared/reference/csize-class.md) 링크 컨트롤의 새 크기를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl 클래스](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md)
