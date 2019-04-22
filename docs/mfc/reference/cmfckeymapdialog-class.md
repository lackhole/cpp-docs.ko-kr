---
title: CMFCKeyMapDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: 65aa5ab0f24999ee23a97f383577b69584825502
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774791"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog 클래스

`CMFCKeyMapDialog` 클래스 명령을 키보드의 키에 매핑되는 컨트롤을 지원 합니다.

## <a name="syntax"></a>구문

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|`CMFCKeyMapDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCKeyMapDialog::DoModal](#domodal)|키보드 매핑 대화 상자를 표시합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCKeyMapDialog::FormatItem](#formatitem)|키 매핑을 설명 하는 문자열을 작성 하기 위해 프레임 워크에서 호출 됩니다. 기본적으로 문자열 명령 이름, 사용, 바로 가기 키 및 바로 가기 키 설명을 포함 합니다.|
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|지정 된 명령과 사용 하 여 연결 된 바로 가기 키의 목록을 포함 하는 문자열을 검색 합니다.|
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤에 새 항목을 삽입 하기 전에 프레임 워크에서 호출 됩니다.|
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|새 페이지에는 키보드 맵과 대 한 머리글을 인쇄 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|키보드 매핑 항목을 인쇄 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤의 열에 대 한 캡션을 설정 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|사용자가 클릭할 때 프레임 워크에서 호출 된 **인쇄** 단추입니다.|
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤에서 열 너비를 설정 하기 위해 프레임 워크에서 호출 됩니다.|

## <a name="remarks"></a>설명

사용 된 `CMFCKeyMapDialog` 크기 조정 가능한 키보드 매핑 대화 상자를 구현 하는 클래스입니다. 대화 상자는 바로 가기 키 및 관련된 명령을 표시 하는 목록 뷰 컨트롤을 사용 합니다.

사용 하는 `CMFCKeyMapDialog` 응용 프로그램에서 클래스를 매개 변수로 주 프레임 창에 대 한 포인터에 전달 된 `CMFCKeyMapDialog` 생성자입니다. 그런 다음 호출을 `DoModal` 모달 대화 상자를 시작 하는 방법입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxkeymapdialog.h

##  <a name="cmfckeymapdialog"></a>  CMFCKeyMapDialog::CMFCKeyMapDialog

`CMFCKeyMapDialog` 개체를 생성합니다.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>매개 변수

*pWndParentFrame*<br/>
[in] 부모 창에 대 한 포인터를 `CMFCKeyMapDialog` 개체입니다.

*bEnablePrint*<br/>
[in] TRUE 이면 액셀러레이터 키 목록을 인쇄할 수 있습니다. 그렇지 않으면 FALSE입니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCKeyMapDialog` 클래스입니다. 이 예제는의 일부를 [Visual Studio 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal

키보드 매핑 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

IDOK 등 IDCANCEL에 전달 되는 부호 있는 정수인 합니다 [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) 메서드. 메서드는 차례로 대화 상자를 닫습니다. 자세한 내용은 [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal)합니다.

### <a name="remarks"></a>설명

키보드 매핑 대화 상자를 선택 하 고 다양 한 범주의 명령 액셀러레이터 키를 할당할 수 있습니다. 또한 선택한 바로 가기 키 및 해당 설명을 클립보드로 복사할 수 있습니다.

##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem

키 매핑을 설명 하는 문자열을 작성 하기 위해 프레임 워크에서 호출 됩니다. 기본적으로 문자열 명령 이름, 사용, 바로 가기 키 및 바로 가기 키 설명을 포함 합니다.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
[in] 키 매핑 내부 목록에 있는 항목의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

`CString` 서식이 지정 된 항목 텍스트를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys

문자열 값을 검색 합니다. 지정 된 명령과 사용 하 여 연결 된 바로 가기 키의 목록을 포함 하는 문자열입니다.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
[in] 명령 id입니다.

### <a name="return-value"></a>반환 값

세미콜론으로 구분 된 지정 된 명령과 사용 하 여 연결 된 바로 가기 키 (';') 목록입니다.

### <a name="remarks"></a>설명

##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem

키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤에 새 항목을 삽입 하기 전에 프레임 워크에서 호출 됩니다.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>매개 변수

*pButton*<br/>
[in] 키보드 키 조합을 명령 이름 및 설명에 매핑할 때 사용 되는 도구 모음 단추에 대 한 포인터입니다. 주요 map 항목은 내부 목록 컨트롤에 저장 됩니다.

*nItem*<br/>
[in] 내부 목록 컨트롤에 새 키 맵에서 항목을 삽입할 위치를 지정 하는 0부터 시작 인덱스입니다.

### <a name="remarks"></a>설명

##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader

새 페이지에는 키보드 맵과 대 한 머리글을 인쇄 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>매개 변수

*dc*<br/>
[in] 프린터 디바이스 컨텍스트입니다.

*nPage*<br/>
[in] 인쇄할 페이지 번호입니다.

*cx*<br/>
[in] 픽셀에서 헤더의 가로 오프셋입니다.

### <a name="return-value"></a>반환 값

성공 하면 인쇄 되는 텍스트의 높이입니다. 자세한 내용은의 반환 값 섹션을 참조 하세요. [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)합니다.

### <a name="remarks"></a>설명

프레임 워크는 키보드 맵과 인쇄 하려면이 메서드를 사용 합니다. 기본적으로이 메서드는 페이지 번호, 응용 프로그램 이름 및 대화 상자 제목을 인쇄합니다.

##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem

키보드 매핑 항목을 인쇄 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>매개 변수

*dc*<br/>
[in] 프린터 디바이스 컨텍스트입니다.

*nItem*<br/>
[in] 인쇄 항목의 0부터 시작 하는 인덱스입니다.

*y*<br/>
[in] 항목의 위치 페이지의 위쪽 사이의 세로 오프셋입니다.

*cx*<br/>
[in] 항목의 위치 페이지의 왼쪽 사이의 가로 오프셋입니다.

*bCalcHeight*<br/>
[in] 최상의 인쇄 항목 높이 계산. False 이면 기본 공간에 맞도록 인쇄 항목이 잘립니다.

### <a name="return-value"></a>반환 값

인쇄 된 항목의 높이입니다.

### <a name="remarks"></a>설명

프레임 워크 키 지도 대화 상자 항목을 인쇄 하려면이 메서드를 호출 합니다. 기본적으로이 메서드 출력 항목의 명령 이름, 바로 가기 키 및 명령 설명 합니다.

##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns

키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤의 열에 대 한 캡션을 설정 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>설명

기본적으로이 메서드는 세 가지 리소스에서 열에 대 한 캡션을 가져옵니다. 명령 열 캡션 IDS_AFXBARRES_COMMAND에서, 키 열 캡션 IDS_AFXBARRES_KEYS에서 이며 설명 열 캡션 IDS_AFXBARRES_DESCRIPTION에서 됩니다.

##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap

사용자가 클릭할 때 프레임 워크에서 호출 된 **인쇄** 단추입니다.

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>설명

`PrintKeyMap` 메서드 주요 map을 인쇄 합니다. 새 인쇄 작업을 시작 하 고 반복적으로 호출 합니다 [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) 하 고 [CMFCKeyMapDialog::OnPrintItem](#onprintitem) 모든 키 매핑을 인쇄 될 때까지 메서드.

##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth

키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤에서 열 너비를 설정 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>설명

이 메서드가 기본 너비를 내부 목록 컨트롤의 열으로 설정 합니다. 첫째, 바로 가기 키 열의 너비를 계산 됩니다. 그런 다음 1 / 3의 나머지 너비를 명령 열에 할당 하 고 나머지 2 / 3 설명 열에 할당 됩니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)
