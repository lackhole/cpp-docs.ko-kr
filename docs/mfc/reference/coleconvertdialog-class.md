---
title: COleConvertDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
ms.openlocfilehash: d0d2f83a6340224cf0fd6318e470fcfae103d72b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310411"
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog 클래스

자세한 내용은 참조는 [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Windows SDK에는 구조입니다.

## <a name="syntax"></a>구문

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|`COleConvertDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleConvertDialog::DoConvert](#doconvert)|대화 상자에 지정 된 변환을 수행 합니다.|
|[COleConvertDialog::DoModal](#domodal)|OLE 변경 항목 대화 상자를 표시합니다.|
|[COleConvertDialog::GetClassID](#getclassid)|선택한 항목에 연결 된 CLSID를 가져옵니다.|
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|항목 아이콘으로 그릴 것인지를 지정 합니다.|
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 아이콘을 폼에 연결 된 메타 파일에 대 한 핸들을 가져옵니다.|
|[COleConvertDialog::GetSelectionType](#getselectiontype)|선택한 항목의 형식을 가져옵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|대화 상자의 동작을 제어 하는 구조체입니다.|

## <a name="remarks"></a>설명

> [!NOTE]
>  응용 프로그램 컨테이너 마법사에서 생성 된 코드는이 클래스를 사용합니다.

OLE 관련 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog

만 생성을 `COleConvertDialog` 개체입니다.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
변환 되거나 활성화 항목을 가리킵니다.

*dwFlags*<br/>
원하는 수의 다음 값을 포함 하는 생성 플래그 비트를 사용 하 여 결합-or 연산자:

- CF_SELECTCONVERTTO 변환 라디오 단추가 되도록 지정 선택 대화 상자를 호출할 때. 이 값이 기본값입니다.

- CF_SELECTACTIVATEAS 지정으로 활성화 라디오 단추 수 있는 선택 대화 상자를 호출할 때.

- CF_SETCONVERTDEFAULT 지정 된 CLSID 지정 된 클래스를 `clsidConvertDefault` 소속을 `m_cv` 구조 변환 라디오 단추를 선택한 경우 클래스 목록 상자에서 기본 선택으로 사용 됩니다.

- CF_SETACTIVATEDEFAULT 지정 된 CLSID 지정 된 클래스를 `clsidActivateDefault` 소속을 `m_cv` 활성화로 라디오 단추를 선택할 때 구조 클래스 목록 상자에서 기본 선택으로 사용 됩니다.

- CF_SHOWHELPBUTTON는 도움말 단추가 대화 상자를 호출할 때 표시 되도록 지정 합니다.

*pClassID*<br/>
활성화 또는 변환 항목의 CLSID 가리킵니다. CLSID 연결 된 값이 null 이면 *pItem* 사용 됩니다.

*pParentWnd*<br/>
부모 또는 소유자 창 개체 (형식의 `CWnd`) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자의 부모 창 주 응용 프로그램 창으로 설정 됩니다.

### <a name="remarks"></a>설명

대화 상자를 표시 하려면 호출을 [DoModal](#domodal) 함수입니다.

자세한 내용은 [CLSID 키](/windows/desktop/com/clsid-key-hklm) 하며 [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) 구조입니다.

##  <a name="doconvert"></a>  COleConvertDialog::DoConvert

성공적으로 반환 된 후이 함수를 호출 [DoModal](#domodal), 변환 또는 형식의 개체를 활성화 하거나 [COleClientItem](../../mfc/reference/coleclientitem-class.md)합니다.

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
변환 되거나 활성화 항목을 가리킵니다. NULL일 수 없습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

항목을 변환 또는 변환 대화 상자에서 사용자가 선택한 정보에 따라 활성화 됩니다.

##  <a name="domodal"></a>  COleConvertDialog::DoModal

OLE 변환 대화 상자를 표시 하려면이 함수를 호출 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.

- IDOK 대화 상자를 성공적으로 표시 된 경우입니다.

- 사용자가 대화 상자를 취소 하는 경우 IDCANCEL 합니다.

- IDABORT 오류가 발생 합니다. IDABORT 반환 되 면 호출 된 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 발생 한 오류 유형에 대 한 자세한 정보를 보려면 멤버 함수입니다. 목록을 가능한 오류에 대 한 참조를 [OleUIConvert](/windows/desktop/api/oledlg/nf-oledlg-oleuiconverta) Windows SDK에는 함수입니다.

### <a name="remarks"></a>설명

멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_cv](#m_cv) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체에서 생성 된 후 있지만.

경우 `DoModal` IDOK 반환 다른 멤버를 설정 또는 사용자가 대화 상자에 입력 된 정보를 검색 하는 함수를 호출할 수 있습니다.

##  <a name="getclassid"></a>  COleConvertDialog::GetClassID

변환 대화 상자에서 사용자가 선택한 항목과 연결 된 CLSID를 가져오려면이 함수를 호출 합니다.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>반환 값

변환 대화 상자에서 선택한 항목에 연결 된 CLSID입니다.

### <a name="remarks"></a>설명

한 후에이 함수 호출 [DoModal](#domodal) IDOK를 반환 합니다.

자세한 내용은 [CLSID 키](/windows/desktop/com/clsid-key-hklm) Windows SDK에 있습니다.

##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect

선택한 항목을 아이콘으로 표시 하려면 사용자가 있는지 여부를 결정 하는이 함수를 호출 합니다.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>반환 값

개체를 렌더링 하는 데 필요한 메서드입니다.

- DVASPECT_CONTENT 아이콘으로 표시 확인란을 선택 하지 않은 경우 반환 됩니다.

- DVASPECT_ICON 아이콘으로 표시 확인란을 선택 된 경우 반환 됩니다.

### <a name="remarks"></a>설명

한 후에이 함수 호출 [DoModal](#domodal) IDOK를 반환 합니다.

그리기 측면에 대 한 자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 데이터 구조입니다.

##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile

선택한 항목의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들을 가져오려면이 함수를 호출 합니다.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>반환 값

아이콘으로 표시 확인란 되었으면 선택한 항목의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들 확인;를 선택 하 여 대화 상자를 해제 하는 경우 확인 그렇지 않으면 NULL입니다.

##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType

변환 대화 상자에서 선택 하는 변환 형식을 결정 하는이 함수를 호출 합니다.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>반환 값

선택한 옵션의 형식입니다.

### <a name="remarks"></a>설명

반환 형식이 값으로 지정 됩니다는 `Selection` 에 선언 된 열거형의 `COleConvertDialog` 클래스.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

이러한 값에 대 한 간략 한 설명을 따릅니다.

- `COleConvertDialog::noConversion` 대화 상자를 취소 하거나 사용자가 선택한 변환 작업 없이 반환 합니다. 경우 `COleConvertDialog::DoModal` IDOK 반환 있기 사용자 하나 이전에 선택한 다른 아이콘을 선택 하 합니다.

- `COleConvertDialog::convertItem` 사용자가 다른 항목으로 변환할 선택한 변환 라디오 단추를 선택 하는 경우 반환 하 고 `DoModal` IDOK 반환 합니다.

- `COleConvertDialog::activateAs` 사용자를 활성화 하려면 다른 항목을 선택한 다른 이름으로 활성화 라디오 단추를 선택 하는 경우 반환 되 고 `DoModal` IDOK 반환 합니다.

##  <a name="m_cv"></a>  COleConvertDialog::m_cv

OLEUICONVERT 형식의 구조 변환 대화 상자의 동작을 제어 하는 데 사용 합니다.

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>설명

이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 참조는 [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Windows SDK에는 구조입니다.

## <a name="see-also"></a>참고자료

[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
