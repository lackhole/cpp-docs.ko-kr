---
title: COleDropSource 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
ms.openlocfilehash: a2773333ea1dd89f73e7bdf3c5dc2f36945e0810
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58778509"
---
# <a name="coledropsource-class"></a>COleDropSource 클래스

데이터를를 놓기 대상으로 끌어 놓을 수 있습니다.

## <a name="syntax"></a>구문

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleDropSource::COleDropSource](#coledropsource)|`COleDropSource` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleDropSource::GiveFeedback](#givefeedback)|끌어서 놓기 작업 중 커서를 변경합니다.|
|[COleDropSource::OnBeginDrag](#onbegindrag)|끌어서 놓기 작업 중에 마우스 캡처를 처리합니다.|
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|끌어 되는지 여부를 검사를 계속 해야 합니다.|

## <a name="remarks"></a>설명

합니다 [COleDropTarget](../../mfc/reference/coledroptarget-class.md) 클래스는 끌어서 놓기 작업의 수신 부분을 처리 합니다. `COleDropSource` 개체는 끌기 작업을 시작할 때 결정, 끌기 작업 도중 사용자 의견을 제공 및 끌기 작업이 종료 되는 경우를 결정 합니다.

사용 하는 `COleDropSource` 개체 생성자를 호출 합니다. 이 마우스 클릭 같은 이벤트를 사용 하 여 끌기 작업 시작을 확인 하는 과정을 간소화 [coledatasource:: Dodragdrop](../../mfc/reference/coledatasource-class.md#dodragdrop)하십시오 [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), 또는 [ COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) 함수입니다. 이러한 함수를 만듭니다를 `COleDropSource` 개체입니다. 기본 동작을 수정 하려는 경우는 `COleDropSource` 재정의 가능 함수입니다. 이러한 멤버 함수는 프레임 워크에서 적절 한 시간에 호출 됩니다.

OLE를 사용 하 여 끌어서 놓기 작업에 대 한 자세한 내용은 문서 참조 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.

자세한 내용은 [IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource) Windows SDK에 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="coledropsource"></a>  COleDropSource::COleDropSource

`COleDropSource` 개체를 생성합니다.

```
COleDropSource();
```

##  <a name="givefeedback"></a>  COleDropSource::GiveFeedback

호출 후에 프레임 워크에서 호출 [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) 하거나 [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter)합니다.

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>매개 변수

*dropEffect*<br/>
사용자에 게 표시 하려면 원하는 효과 일반적으로 무엇을 나타내는 이러한 문제가 발생 하면 선택한 데이터를 사용 하 여이 지점에서 발생 한 저장 합니다. 일반적으로이 가장 최근 호출에 의해 반환 되는 값 [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) 하거나 [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover)합니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_NONE 저장이 허용 되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행 됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정 됩니다.

- DROPEFFECT_SCROLL는 끌기 스크롤 작업 수행 되려고 하거나 대상에서 발생 합니다.

### <a name="return-value"></a>반환 값

DRAGDROP_S_USEDEFAULTCURSORS 끌어 경우 진행 중인 경우 없으면 NOERROR 반환 합니다.

### <a name="remarks"></a>설명

드롭다운이 시점에서 발생 한 경우 어떻게 하는 방법에 대 한 사용자에 게 피드백을 제공 하려면이 함수를 재정의 합니다. 기본 구현은 OLE 기본 커서를 사용 합니다. OLE를 사용 하 여 끌어서 놓기 작업에 대 한 자세한 내용은 문서 참조 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.

자세한 내용은 [IDropSource::GiveFeedback](/windows/desktop/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget::DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover), 및 [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows sdk에서입니다.

##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag

에 의해 호출 프레임 워크는 이벤트가 발생 하는 경우에 마우스 왼쪽된 단추를 누르면 등의 끌기 작업을 시작할 수 있습니다.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
선택한 데이터를 포함 된 창 가리킵니다.

### <a name="return-value"></a>반환 값

이 속성을 0이 아닌 끌어 허용 된 경우, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

끌기 프로세스가 시작 되는 방식을 수정 하려는 경우이 함수를 재정의 합니다. 기본 구현은 마우스를 캡처하고 사용자가 마우스 왼쪽 또는 오른쪽 단추를 클릭 또는 ESC 키를 마우스 해제 될 때 적중 될 때까지 끌기 모드에 유지 됩니다.

##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag

끌기가 시작 되 면이 함수는 반복적으로 호출 프레임 워크에서 끌기 작업 취소 또는 완료 될 때까지.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>매개 변수

*bEscapePressed*<br/>
마지막으로 호출한 이후 ESC 키를 눌렀는지 여부를 나타내는 `COleDropSource::QueryContinueDrag`합니다.

*dwKeyState*<br/>
키보드의 한정자 키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.

### <a name="return-value"></a>반환 값

ESC 키 또는 오른쪽 단추를 누르면 되었거나 단추 왼쪽 DRAGDROP_S_CANCEL 끌기 시작 전에 발생 합니다. DRAGDROP_S_DROP 놓기 작업이 발생 해야 하는 경우입니다. 그렇지 않은 경우 S_OK입니다.

### <a name="remarks"></a>설명

이 함수는 끌어 시점을 변경 하려는 경우 취소 되는 재정의 또는 drop을 발생 합니다.

기본 구현은 삭제를 시작 또는 다음과 같이 끌기를 취소 합니다. ESC 키 또는 마우스 오른쪽 단추를 누를 때 끌기 작업을 취소 합니다. 마우스 왼쪽된 단추를 끌기 시작 된 후 발생 하는 경우 삭제 작업을 시작 합니다. 이 고, 그렇지 S_OK를 반환 하 고 더 이상 없는 작업을 수행 합니다.

이 함수를 자주 호출 했으므로 최적화 해야 최대한 많이 있습니다.

## <a name="see-also"></a>참고자료

[MFC Sample HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
