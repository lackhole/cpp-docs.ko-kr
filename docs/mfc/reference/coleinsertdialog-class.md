---
title: COleInsertDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
ms.openlocfilehash: 27bf98ea4fe6951624873c1463d50f37558c9234
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781486"
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog 클래스

OLE 개체 삽입 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|`COleInsertDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleInsertDialog::CreateItem](#createitem)|대화 상자에서 선택한 항목을 만듭니다.|
|[COleInsertDialog::DoModal](#domodal)|OLE 개체 삽입 대화 상자를 표시합니다.|
|[COleInsertDialog::GetClassID](#getclassid)|선택한 항목에 연결 된 CLSID를 가져옵니다.|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|아이콘이 표시 된 항목을 그릴 것인지를 알려 줍니다.|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 아이콘을 폼에 연결 된 메타 파일에 대 한 핸들을 가져옵니다.|
|[COleInsertDialog::GetPathName](#getpathname)|대화 상자에서 선택한 파일의 전체 경로 가져옵니다.|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|선택한 개체의 형식을 가져옵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|대화 상자의 동작을 제어 하는 OLEUIINSERTOBJECT 형식의 구조체입니다.|

## <a name="remarks"></a>설명

클래스의 개체를 만들려면 `COleInsertDialog` 이 대화 상자를 호출 하려는 경우. 후는 `COleInsertDialog` 생성 된 개체를 사용할 수 있습니다 합니다 [m_io](#m_io) 값 또는 대화 상자에서 컨트롤의 상태를 초기화 하는 구조입니다. `m_io` OLEUIINSERTOBJECT 형식의 구조입니다. 이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조는 [DoModal](#domodal) 멤버 함수입니다.

> [!NOTE]
>  응용 프로그램 컨테이너 마법사에서 생성 된 코드는이 클래스를 사용합니다.

자세한 내용은 참조는 [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) Windows SDK에는 구조입니다.

OLE 관련 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog

이 함수가 구성만 `COleInsertDialog` 개체입니다.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
원하는 수의 비트 OR 연산자를 사용 하 여 결합할 다음 값을 포함 하는 플래그를 생성 합니다.

- IOF_SHOWHELP는 도움말 단추가 대화 상자를 호출할 때 표시 되도록 지정 합니다.

- IOF_SELECTCREATENEW 지정 라디오 단추를 새로 만들기 수 있는 선택 대화 상자를 호출할 때. 기본값이 며 IOF_SELECTCREATEFROMFILE 함께 사용할 수 없습니다.

- IOF_SELECTCREATEFROMFILE를 지정 하는 파일에서 만들 라디오 단추 수 있는 선택 대화 상자를 호출할 때. IOF_SELECTCREATENEW를 사용 하 여 사용할 수 없습니다.

- 연결 확인란 될 IOF_CHECKLINK 지정 확인 처음 대화 상자를 호출할 때.

- 링크 확인란 IOF_DISABLELINK 지정 대화 상자를 호출할 때 사용 되지 것입니다.

- IOF_CHECKDISPLAYASICON 아이콘으로 표시 확인란은 처음에 선택 됩니다 하 고 현재 아이콘이 표시 됩니다, 대화 상자를 호출할 때 변경 아이콘 단추를 사용할 수 있도록 지정 합니다.

- 대화 상자가 표시 되기 전에 등록 데이터베이스에 지정 된 서버가 존재 하는지 확인 하 여 목록 상자에 추가 IOF_VERIFYSERVERSEXIST 지정 대화 상자 클래스의 유효성을 검사 해야 합니다. 이 플래그를 설정 하면 성능이 크게 저하 수 있습니다.

*pParentWnd*<br/>
부모 또는 소유자 창 개체 (형식의 `CWnd`) 대화 상자 개체 속한 합니다. NULL 인 경우 기본 응용 프로그램 창에 대화 상자 개체의 부모 창이 설정 됩니다.

### <a name="remarks"></a>설명

대화 상자를 표시 하려면 호출을 [DoModal](#domodal) 함수입니다.

##  <a name="createitem"></a>  COleInsertDialog::CreateItem

형식의 개체를 만들려면이 함수를 호출 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 경우에만 [DoModal](#domodal) IDOK를 반환 합니다.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
만들 항목을 가리킵니다.

### <a name="return-value"></a>반환 값

항목이 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

할당 해야 합니다는 `COleClientItem` 이 함수를 호출 하기 전에 개체입니다.

##  <a name="domodal"></a>  COleInsertDialog::DoModal

OLE 개체 삽입 대화 상자를 표시 하려면이 함수를 호출 합니다.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
다음 값 중 하나입니다.

`COleInsertDialog::DocObjectsOnly` 만 DocObjects를 삽입합니다.

`COleInsertDialog::ControlsOnly` 만 ActiveX 컨트롤을 삽입합니다.

DocObject 아니고 ActiveX 컨트롤을 삽입 하는 0입니다. 위에 나열 된 첫 번째 프로토타입으로 동일 하 게 구현에서이 값 결과입니다.

### <a name="return-value"></a>반환 값

대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.

- IDOK 대화 상자를 성공적으로 표시 된 경우입니다.

- 사용자가 대화 상자를 취소 하는 경우 IDCANCEL 합니다.

- IDABORT 오류가 발생 합니다. IDABORT 반환 되 면 호출 된 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 발생 한 오류 유형에 대 한 자세한 정보를 보려면 멤버 함수입니다. 목록을 가능한 오류에 대 한 참조를 [OleUIInsertObject](/windows/desktop/api/oledlg/nf-oledlg-oleuiinsertobjecta) Windows SDK에는 함수입니다.

### <a name="remarks"></a>설명

멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_io](#m_io) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체에서 생성 된 후 있지만.

경우 `DoModal` IDOK 반환 다른 멤버를 설정 또는 사용자가 대화 상자에 정보 입력을 검색 하는 함수를 호출할 수 있습니다.

##  <a name="getclassid"></a>  COleInsertDialog::GetClassID

연결 된 경우에는 선택한 항목만 CLSID를 가져오려면이 함수를 호출 [DoModal](#domodal) IDOK 및 선택 유형을 반환 `COleInsertDialog::createNewItem`합니다.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>반환 값

선택한 항목에 연결 된 CLSID를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [CLSID 키](/windows/desktop/com/clsid-key-hklm) Windows SDK에 있습니다.

##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect

사용자가 선택한 항목 아이콘으로 표시할 경우를 결정 하는이 함수를 호출 합니다.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>반환 값

개체를 렌더링 하는 데 필요한 메서드입니다.

- DVASPECT_CONTENT 아이콘으로 표시 확인란을 선택 하지 않은 경우 반환 됩니다.

- DVASPECT_ICON 아이콘으로 표시 확인란을 선택 된 경우 반환 됩니다.

### <a name="remarks"></a>설명

경우에만이 함수를 호출 [DoModal](#domodal) IDOK를 반환 합니다.

그리기 측면에 대 한 자세한 내용은 참조 하세요. [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 데이터 구조입니다.

##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile

선택한 항목의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들을 가져오려면이 함수를 호출 합니다.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>반환 값

아이콘으로 표시 확인란 되었으면 선택한 항목의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들을 선택 하 여 대화 상자를 해제 하는 경우 체크 **확인**그렇지 않으면 NULL입니다.

##  <a name="getpathname"></a>  COleInsertDialog::GetPathName

경우에만 선택한 파일의 전체 경로 가져오려면이 함수를 호출 [DoModal](#domodal) IDOK 및 선택 유형을 아닙니다 반환 `COleInsertDialog::createNewItem`합니다.

```
CString GetPathName() const;
```

### <a name="return-value"></a>반환 값

대화 상자에서 선택한 파일에 전체 경로입니다. 선택 형식이 `createNewItem`,이 함수는 반환 된 의미 없는 `CString` 릴리스 모드에서 또는 디버그 모드에서 어설션을 발생 시킵니다.

##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType

개체 삽입 대화 상자를 선택 하 여 해제할 때 선택한 선택 유형을 가져오려면이 함수를 호출 **확인**합니다.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>반환 값

선택한 옵션의 형식입니다.

### <a name="remarks"></a>설명

반환 형식이 값으로 지정 됩니다는 `Selection` 에 선언 된 열거형의 `COleInsertDialog` 클래스.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

이러한 값에 대 한 간략 한 설명을 따릅니다.

- `COleInsertDialog::createNewItem` 새로 만들기 라디오 단추를 선택 했습니다.

- `COleInsertDialog::insertFromFile` 파일에서 만들기 라디오 단추를 선택 했습니다. 연결 확인란을 선택 하지 않은 하며

- `COleInsertDialog::linkToFile` 파일에서 만들기 라디오 단추를 선택 했습니다 및 링크 확인란을 선택 했습니다.

##  <a name="m_io"></a>  COleInsertDialog::m_io

OLEUIINSERTOBJECT 형식의 구조체 개체 삽입 대화 상자에서의 동작을 제어 하는 데 사용 합니다.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>설명

이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 참조는 [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) Windows SDK에는 구조입니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
