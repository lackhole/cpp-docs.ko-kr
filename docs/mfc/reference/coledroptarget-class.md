---
title: COleDropTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
helpviewer_keywords:
- COleDropTarget [MFC], COleDropTarget
- COleDropTarget [MFC], OnDragEnter
- COleDropTarget [MFC], OnDragLeave
- COleDropTarget [MFC], OnDragOver
- COleDropTarget [MFC], OnDragScroll
- COleDropTarget [MFC], OnDrop
- COleDropTarget [MFC], OnDropEx
- COleDropTarget [MFC], Register
- COleDropTarget [MFC], Revoke
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
ms.openlocfilehash: 9a1633ed48c763b986f3421c33589a05f8bba126
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781642"
---
# <a name="coledroptarget-class"></a>COleDropTarget 클래스

창과 OLE 라이브러리 사이의 통신 메커니즘을 제공합니다.

## <a name="syntax"></a>구문

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleDropTarget::COleDropTarget](#coledroptarget)|`COleDropTarget` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleDropTarget::OnDragEnter](#ondragenter)|커서를 창에 먼저 들어가면 호출 됩니다.|
|[COleDropTarget::OnDragLeave](#ondragleave)|창 밖으로 커서를 끌 때 호출 됩니다.|
|[COleDropTarget::OnDragOver](#ondragover)|커서를 창 위로 끌 때 반복적으로 호출 합니다.|
|[COleDropTarget::OnDragScroll](#ondragscroll)|커서를 창의 스크롤 영역으로 끄는 여부를 확인 하기 위해 호출 됩니다.|
|[COleDropTarget::OnDrop](#ondrop)|기본 처리기는 창에 데이터를 놓을 때 호출 됩니다.|
|[COleDropTarget::OnDropEx](#ondropex)|초기 처리기 창에 데이터를 놓을 때 호출 됩니다.|
|[COleDropTarget::Register](#register)|창의 유효한 놓기 대상으로 등록합니다.|
|[COleDropTarget::Revoke](#revoke)|창의 유효한 놓기 대상이 되는 것이 중지 하면 됩니다.|

## <a name="remarks"></a>설명

이 클래스의 개체를 만들면 OLE 끌어서 놓기 메커니즘을 통해 데이터를 허용 하도록 창이 있습니다.

Drop 명령에 동의 하는 창을 가져오려면 먼저 만들어야의 개체를 `COleDropTarget` 클래스를 호출 합니다 [등록](#register) 원하는에 대 한 포인터를 사용 하 여 함수 `CWnd` 를 유일한 매개 변수로 개체입니다.

OLE를 사용 하 여 끌어서 놓기 작업에 대 한 자세한 내용은 문서 참조 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="coledroptarget"></a>  COleDropTarget::COleDropTarget

클래스의 개체를 생성 `COleDropTarget`합니다.

```
COleDropTarget();
```

### <a name="remarks"></a>설명

호출 [등록](#register) 창을 사용 하 여이 개체를 연결 합니다.

##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter

커서를 먼저 창으로 끌 때 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서를 입력 하는 창을 가리킵니다.

*pDataObject*<br/>
삭제할 수 있는 데이터를 포함 하는 데이터 개체를 가리킵니다.

*dwKeyState*<br/>
보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.

*point*<br/>
클라이언트 좌표에서 커서의 현재 위치를 포함합니다.

### <a name="return-value"></a>반환 값

삭제 하 여 지정 된 위치에서 시도한 경우 초래 하는 효과 *지점*합니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_NONE 저장이 허용 되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행 됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정 됩니다.

- DROPEFFECT_SCROLL는 끌기 스크롤 작업 수행 되려고 하거나 대상에서 발생 합니다.

### <a name="remarks"></a>설명

놓기 작업을 창에서 수행할 수 있도록이 함수를 재정의 합니다. 기본 구현 호출 [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), 단순히 DROPEFFECT_NONE 기본적으로 반환 합니다.

자세한 내용은 [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows SDK에 있습니다.

##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave

커서 끌기 작업이 적용 되는 동안 창을 벗어날 때 프레임 워크에서 호출 됩니다.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
지점 커서 창에 그대로 유지 합니다.

### <a name="remarks"></a>설명

끌기 작업 지정된 된 기간을 벗어날 때 특별 한 동작을 원하는 경우이 함수를 재정의 합니다. 이 함수의 기본 구현이 호출 [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)합니다.

자세한 내용은 [IDropTarget::DragLeave](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragleave) Windows SDK에 있습니다.

##  <a name="ondragover"></a>  COleDropTarget::OnDragOver

커서를 창 위로 끌 때 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서를 창으로 가리킵니다.

*pDataObject*<br/>
삭제 될 데이터가 포함 된 데이터 개체를 가리킵니다.

*dwKeyState*<br/>
보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.

*point*<br/>
클라이언트 좌표에서 커서의 현재 위치를 포함합니다.

### <a name="return-value"></a>반환 값

삭제 하 여 지정 된 위치에서 시도한 경우 초래 하는 효과 *지점*합니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_NONE 저장이 허용 되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행 됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정 됩니다.

- DROPEFFECT_SCROLL 끌기 스크롤 작업을 수행 하려고 합니다. 또는 대상에서 발생 했음을 나타냅니다.

### <a name="remarks"></a>설명

놓기 작업을 창에서 수행할 수 있도록이 함수를 재정의 해야 합니다. 이 함수의 기본 구현이 호출 [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), DROPEFFECT_NONE 기본적으로 반환 합니다. 이 함수를 끌어서 놓기 작업 동안 자주 호출 했으므로 최적화 해야 최대한 많이 합니다.

자세한 내용은 [IDropTarget::DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll

호출 하기 전에 프레임 워크에서 호출 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 결정할 여부 *가리킨* 스크롤 영역에는 합니다.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서를 현재 창 가리킵니다.

*dwKeyState*<br/>
보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.

*point*<br/>
커서를 화면을 기준으로 픽셀의 위치를 포함 합니다.

### <a name="return-value"></a>반환 값

삭제 하 여 지정 된 위치에서 시도한 경우 초래 하는 효과 *지점*합니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_NONE 저장이 허용 되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행 됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정 됩니다.

- DROPEFFECT_SCROLL 끌기 스크롤 작업을 수행 하려고 합니다. 또는 대상에서 발생 했음을 나타냅니다.

### <a name="remarks"></a>설명

이 이벤트에 대 한 특별 한 동작을 제공 하려는 경우이 함수를 재정의 합니다. 이 함수의 기본 구현이 호출 [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), DROPEFFECT_NONE 반환 하며 기본 스크롤 영역 창의 테두리 내부에 커서를 끌 때 창을 스크롤합니다.

##  <a name="ondrop"></a>  COleDropTarget::OnDrop

놓기 작업이 발생 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서를 현재 창 가리킵니다.

*pDataObject*<br/>
삭제 될 데이터가 포함 된 데이터 개체를 가리킵니다.

*dropEffect*<br/>
Drop 작업에 대 한 사용자가 선택 하는 효과입니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_COPY 복사 작업이 수행 됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정 됩니다.

*point*<br/>
커서를 화면을 기준으로 픽셀의 위치를 포함 합니다.

### <a name="return-value"></a>반환 값

드롭다운에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Framework 첫 번째 호출은 [OnDropEx](#ondropex)합니다. 경우는 `OnDropEx` 함수를 처리 하지 않습니다, 프레임 워크를이 멤버 함수를 호출 `OnDrop`합니다. 일반적으로 응용 프로그램 재정의 [OnDropEx](../../mfc/reference/cview-class.md#ondropex) 마우스 오른쪽 단추를 처리 하는 뷰 클래스에 놓습니다. 일반적으로 뷰 클래스 [OnDrop](../../mfc/reference/cview-class.md#ondrop) 간단한 끌어서 놓기를 처리 하는 데 사용 됩니다.

기본 구현의 `COleDropTarget::OnDrop` 호출 [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), 단순히 기본적으로 FALSE 반환 합니다.

자세한 내용은 [IDropTarget::Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) Windows SDK에 있습니다.

##  <a name="ondropex"></a>  COleDropTarget::OnDropEx

놓기 작업이 발생 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서를 현재 창 가리킵니다.

*pDataObject*<br/>
삭제 될 데이터가 포함 된 데이터 개체를 가리킵니다.

*dropDefault*<br/>
현재 키 상태를 기반으로 기본 놓기 작업에 대 한 사용자가 선택 하는 효과입니다. DROPEFFECT_NONE 수 있습니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 합니다.

*dropList*<br/>
목록 놓기 소스가 지원 되는 놓기 효과입니다. 비트 OR를 사용 하 여 드롭 효과 값을 결합할 수 있습니다 (**&#124;**) 작업입니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 합니다.

*point*<br/>
커서를 화면을 기준으로 픽셀의 위치를 포함 합니다.

### <a name="return-value"></a>반환 값

지정 된 위치에서 삭제 시도에서 발생 하는 놓기 효과 *지점*합니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 합니다.

### <a name="remarks"></a>설명

프레임 워크는 먼저이 함수를 호출합니다. 프레임 워크는 다음 호출의 삭제를 처리 하지 않습니다 [OnDrop](#ondrop)합니다. 일반적으로 재정의 [OnDropEx](../../mfc/reference/cview-class.md#ondropex) 마우스 오른쪽 단추를 지원 하기 위해 뷰 클래스에 놓습니다. 일반적으로 뷰 클래스 [OnDrop](../../mfc/reference/cview-class.md#ondrop) 간단한 끌어서 놓기에 대 한 지원 사례를 처리 하는 데 사용 됩니다.

기본 구현의 `COleDropTarget::OnDropEx` 호출 [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)합니다. 기본적으로 [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) 간단히 나타내기 위해 더미 값을 반환 합니다 [OnDrop](#ondrop) 멤버 함수를 호출 해야 합니다.

끌어서 놓기 작업 결과 놓기 작업을 사용 하 여 연결 된 동작을 설명 합니다. 끌어서 놓기 작업 결과의 다음 목록을 참조 하세요.

- DROPEFFECT_NONE 저장이 허용 되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행 됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정 됩니다.

- DROPEFFECT_SCROLL 끌기 스크롤 작업을 수행 하려고 합니다. 또는 대상에서 발생 했음을 나타냅니다.

자세한 내용은 [IDropTarget::Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) Windows SDK에 있습니다.

##  <a name="register"></a>  COleDropTarget::Register

창 OLE Dll 유효한 놓기 대상으로 등록 하려면이 함수를 호출 합니다.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
놓기 대상으로 등록 하는 창 가리킵니다.

### <a name="return-value"></a>반환 값

등록에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

허용할 놓기 작업에 대 한이 함수를 호출 해야 합니다.

자세한 내용은 [RegisterDragDrop](/windows/desktop/api/ole2/nf-ole2-registerdragdrop) Windows SDK에 있습니다.

##  <a name="revoke"></a>  COleDropTarget::Revoke

호출을 통해 놓기 대상으로 등록 된 모든 창을 제거 하기 전에이 함수를 호출 [등록](#register) 놓기 대상의 목록에서 제거 합니다.

```
virtual void Revoke();
```

### <a name="remarks"></a>설명

이 함수를 자동으로 호출 합니다 [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) 일반적으로 필요 없는이 함수를 명시적으로 호출 하도록 등록 된 창에 대 한 처리기입니다.

자세한 내용은 [RevokeDragDrop](/windows/desktop/api/ole2/nf-ole2-revokedragdrop) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[MFC Sample HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource 클래스](../../mfc/reference/coledropsource-class.md)
