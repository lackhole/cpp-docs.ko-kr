---
title: COlePasteSpecialDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
ms.openlocfilehash: 9c31ed6f82f4280206bf233999fac74981636db3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776910"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog 클래스

OLE 선택하여 붙여넣기 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|`COlePasteSpecialDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COlePasteSpecialDialog::AddFormat](#addformat)|사용자 지정 형식을 응용 프로그램에 붙여 넣을 수 있는 형식의 목록에 추가 합니다.|
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|지원 되는 클립보드 형식의 목록에 새 항목을 추가 합니다.|
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|CF_BITMAP, CF_DIB, CF_METAFILEPICT를 추가 하 고 필요에 따라 CF_LINKSOURCE 형식 목록에 응용 프로그램 붙여 넣을 수 있습니다.|
|[COlePasteSpecialDialog::CreateItem](#createitem)|지정 된 형식을 사용 하 여 컨테이너 문서의 항목을 만듭니다.|
|[COlePasteSpecialDialog::DoModal](#domodal)|OLE 붙여넣기 대화 상자를 표시합니다.|
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|그릴 항목 아이콘으로 인지 여부를 알려 줍니다.|
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 아이콘을 폼에 연결 된 메타 파일에 대 한 핸들을 가져옵니다.|
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|사용자가 선택한 사용 가능한 붙여넣기 옵션의 인덱스를 가져옵니다.|
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|선택한 항목의 형식을 가져옵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COlePasteSpecialDialog::m_ps](#m_ps)|대화 상자의 함수를 제어 하는 OLEUIPASTESPECIAL 형식의 구조체입니다.|

## <a name="remarks"></a>설명

클래스의 개체를 만들려면 `COlePasteSpecialDialog` 이 대화 상자를 호출 하려는 경우. 후는 `COlePasteSpecialDialog` 생성 된 개체를 사용할 수 있습니다 합니다 [AddFormat](#addformat) 및 [AddStandardFormats](#addstandardformats) 대화 상자에 클립보드 형식을 추가 하는 멤버 함수입니다. 사용할 수도 있습니다는 [m_ps](#m_ps) 구조 값 또는 대화 상자에서 컨트롤의 상태를 초기화 합니다. `m_ps` OLEUIPASTESPECIAL 형식의 구조입니다.

자세한 내용은 참조는 [OLEUIPASTESPECIAL](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipastespeciala) Windows SDK에는 구조입니다.

OLE 관련 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

##  <a name="addformat"></a>  COlePasteSpecialDialog::AddFormat

응용 프로그램에서 붙여넣기 작업을 지원할 수 있습니다 하는 형식 목록에 새 형식을 추가 하려면이 함수를 호출 합니다.

```
void AddFormat(
    const FORMATETC& formatEtc,
    LPTSTR lpszFormat,
    LPTSTR lpszResult,
    DWORD flags);

void AddFormat(
    UINT cf,
    DWORD tymed,
    UINT nFormatID,
    BOOL bEnableIcon,
    BOOL bLink);
```

### <a name="parameters"></a>매개 변수

*fmt*<br/>
추가할 데이터 형식에 대 한 참조입니다.

*lpszFormat*<br/>
사용자에 게 설명 하는 문자열입니다.

*lpszResult*<br/>
대화 상자에서이 형식을 선택 하는 경우 결과 설명 하는 문자열입니다.

*flags*<br/>
다른 연결 및이 형식에 사용할 수 있는 옵션을 포함 합니다. 이 플래그는 하나의 조합 또는 형식 열거는 OLEUIPASTEFLAG에 다른 값입니다.

*cf*<br/>
추가할 클립보드 형식입니다.

*tymed*<br/>
이 형식에서 사용할 수 있는 미디어의 형식입니다. 비트 조합 또는 형식 열거는 TYMED의 값입니다.

*nFormatID*<br/>
이 형식을 식별 하는 문자열의 ID입니다. 이 문자열의 형식은 '\n' 문자로 구분 된 두 개의 별도 문자열입니다. 에 전달 되는 동일한 첫 번째 문자열은는 *lpstrFormat* 매개 변수를 나타내고 두 번째는 동일 합니다 *lpstrResult* 매개 변수.

*bEnableIcon*<br/>
목록 상자에서이 형식을 선택 하는 경우 아이콘으로 표시 확인란을 사용할 수 있는지 여부를 결정 하는 플래그입니다.

*bLink*<br/>
목록 상자에서이 형식을 선택 하는 경우 연결 하 여 붙여넣기 라디오 단추를 사용할 수 있는지 여부를 결정 하는 플래그입니다.

### <a name="remarks"></a>설명

CF_TEXT 또는 CF_TIFF와 같은 표준 형식 또는 사용자 지정 형식 시스템을 사용 하 여 응용 프로그램 등록을 추가 하려면이 함수를 호출할 수 있습니다. 응용 프로그램에 데이터 개체를 붙여 넣는 방법에 대 한 자세한 내용은 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

자세한 내용은 참조는 [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed) 열거형 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 구조입니다.

자세한 내용은 참조 하세요. 합니다 [OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) Windows SDK의 유형을 열거 합니다.

##  <a name="addlinkentry"></a>  COlePasteSpecialDialog::AddLinkEntry

지원 되는 클립보드 형식의 목록에 새 항목을 추가 합니다.

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>매개 변수

*cf*<br/>
추가할 클립보드 형식입니다.

### <a name="return-value"></a>반환 값

[OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) 새 링크 항목에 대 한 정보가 포함 된 구조입니다.

##  <a name="addstandardformats"></a>  COlePasteSpecialDialog::AddStandardFormats

응용 프로그램에서 붙여넣기 작업을 지원할 수 있습니다 하는 형식 목록에 다음 클립보드 형식을 추가 하려면이 함수를 호출 합니다.

```
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnableLink*<br/>
응용 프로그램 CF_LINKSOURCE 형식 목록에 추가할지 여부를 결정 하는 플래그를 붙여 넣을 수 있습니다.

### <a name="remarks"></a>설명

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"포함 된 개체"**

- (선택 사항) **"Link 원본"**

이러한 형식은 포함 하 고 연결을 지원 하기 위해 사용 됩니다.

##  <a name="colepastespecialdialog"></a>  COlePasteSpecialDialog::COlePasteSpecialDialog

`COlePasteSpecialDialog` 개체를 생성합니다.

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
생성 플래그 비트 OR 연산자를 사용 하 여 결합 하는 다음 플래그를 개수에 관계 없이 포함 됩니다.

- PSF_SELECTPASTE 지정 붙여넣기 라디오 단추가 되도록 확인 처음 대화 상자를 호출할 때. PSF_SELECTPASTELINK와 함께에서 사용할 수 없습니다. 이 값이 기본값입니다.

- PSF_SELECTPASTELINK 지정 링크 붙여넣기 라디오 단추가 될 확인 처음 대화 상자를 호출할 때. PSF_SELECTPASTE와 함께에서 사용할 수 없습니다.

- PSF_CHECKDISPLAYASICON 지정 확인란 아이콘으로 표시 되도록 확인 처음 대화 상자를 호출할 때.

- PSF_SHOWHELP는 도움말 단추가 대화 상자를 호출할 때 표시 되도록 지정 합니다.

*pDataObject*<br/>
가리키는 합니다 [COleDataObject](../../mfc/reference/coledataobject-class.md) 붙여넣기에 대 한 합니다. 이 값이 NULL 인 경우 가져옵니다를 `COleDataObject` 클립보드에 저장에서 합니다.

*pParentWnd*<br/>
부모 또는 소유자 창 개체 (형식의 `CWnd`) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자의 부모 창 주 응용 프로그램 창으로 설정 됩니다.

### <a name="remarks"></a>설명

이 함수 에서만 생성을 `COlePasteSpecialDialog` 개체입니다. 대화 상자를 표시 하려면 호출을 [DoModal](#domodal) 함수입니다.

자세한 내용은 참조 하세요. 합니다 [OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) Windows SDK의 유형을 열거 합니다.

##  <a name="createitem"></a>  COlePasteSpecialDialog::CreateItem

선택 하 여 붙여넣기 대화 상자에서 선택 된 새 항목을 만듭니다.

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>매개 변수

*pNewItem*<br/>
가리키는 `COleClientItem` 인스턴스. NULL일 수 없습니다.

### <a name="return-value"></a>반환 값

항목이 성공적으로 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

후에이 함수를 호출 해야 [DoModal](#domodal) IDOK를 반환 합니다.

##  <a name="domodal"></a>  COlePasteSpecialDialog::DoModal

OLE 붙여넣기 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.

- IDOK 대화 상자를 성공적으로 표시 된 경우입니다.

- 사용자가 대화 상자를 취소 하는 경우 IDCANCEL 합니다.

- IDABORT 오류가 발생 합니다. IDABORT 반환 되 면 호출 된 `COleDialog::GetLastError` 발생 한 오류 유형에 대 한 자세한 정보를 보려면 멤버 함수입니다. 목록을 가능한 오류에 대 한 참조를 [OleUIPasteSpecial](/windows/desktop/api/oledlg/nf-oledlg-oleuipastespeciala) Windows SDK에는 함수입니다.

### <a name="remarks"></a>설명

멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_ps](#m_ps) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체에서 생성 된 후 있지만.

경우 `DoModal` IDOK 반환 함수를 설정 또는 사용자가 정보 입력 대화 상자에 검색할 다른 멤버를 호출할 수 있습니다.

##  <a name="getdrawaspect"></a>  COlePasteSpecialDialog::GetDrawAspect

사용자가 선택한 항목 아이콘으로 표시할 경우를 결정 합니다.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>반환 값

개체를 렌더링 하는 데 필요한 메서드입니다.

- DVASPECT_CONTENT 아이콘으로 표시 확인란 하지 못한 경우 반환 된 대화 상자를 닫을 때 검사 합니다.

- 아이콘으로 표시 된 확인란이 선택 대화 상자를 닫을 때 DVASPECT_ICON 반환 합니다.

### <a name="remarks"></a>설명

후이 함수를 호출한 [DoModal](#domodal) IDOK를 반환 합니다.

그리기 측면에 대 한 자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 구조입니다.

##  <a name="geticonicmetafile"></a>  COlePasteSpecialDialog::GetIconicMetafile

사용자가 선택한 항목에 연결 된 메타 파일을 가져옵니다.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>반환 값

대화 상자를 선택 하 여 해제할 때 아이콘으로 표시 확인란을 선택한 경우 선택한 항목의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들 **확인**그렇지 않으면 NULL입니다.

##  <a name="getpasteindex"></a>  COlePasteSpecialDialog::GetPasteIndex

가져옵니다 인덱스 값을 항목에 연결 된 사용자가 선택한 합니다.

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>반환 값

배열의 인덱스 `OLEUIPASTEENTRY` 사용자가 선택 된 구조입니다. 선택한 인덱스에 해당 하는 형식 붙여넣기 작업을 수행할 때 사용할 해야 합니다.

### <a name="remarks"></a>설명

자세한 내용은 참조는 [OLEUIPASTEENTRY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipasteentrya) Windows SDK에는 구조입니다.

##  <a name="getselectiontype"></a>  COlePasteSpecialDialog::GetSelectionType

사용자 선택 항목의 유형을 결정 합니다.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>반환 값

선택한 옵션의 반환 형식입니다.

### <a name="remarks"></a>설명

반환 형식이 값으로 지정 됩니다는 `Selection` 에 선언 된 열거형의 `COlePasteSpecialDialog` 클래스.

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

이러한 값에 대 한 간략 한 desccriptions를 수행합니다.

- `COlePasteSpecialDialog::pasteLink` 연결 하 여 붙여넣기 라디오 단추를 검사 하 고 선택한 형식이 표준 OLE 형식 되었습니다.

- `COlePasteSpecialDialog::pasteNormal` 붙여넣기 라디오 단추를 검사 하 고 선택한 형식이 표준 OLE 형식 되었습니다.

- `COlePasteSpecialDialog::pasteOther` 선택한 형식 표준 OLE 형식이 아닙니다.

- `COlePasteSpecialDialog::pasteStatic` 선택한 형식의 경우 메타 파일

##  <a name="m_ps"></a>  COlePasteSpecialDialog::m_ps

OLEUIPASTESPECIAL 형식의 구조를 선택 하 여 붙여넣기 대화 상자의 동작을 제어 하는 데 사용 합니다.

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>설명

이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 참조는 [OLEUIPASTESPECIAL](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipastespeciala) Windows SDK에는 구조입니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
