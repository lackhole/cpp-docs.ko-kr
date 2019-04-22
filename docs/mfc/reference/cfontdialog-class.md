---
title: CFontDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
ms.openlocfilehash: b711ca65e552d495e466ea2e46a6779cf43ecbe3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767746"
---
# <a name="cfontdialog-class"></a>CFontDialog 클래스

글꼴 선택 대화 상자를 응용 프로그램에 통합할 수 있습니다.

## <a name="syntax"></a>구문

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFontDialog::CFontDialog](#cfontdialog)|`CFontDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFontDialog::DoModal](#domodal)|대화 상자를 표시 및 선택할 수 있습니다.|
|[CFontDialog::GetCharFormat](#getcharformat)|선택한 글꼴의 문자 형식을 검색 합니다.|
|[CFontDialog::GetColor](#getcolor)|선택한 글꼴의 색을 반환합니다.|
|[CFontDialog::GetCurrentFont](#getcurrentfont)|현재 선택한 글꼴의 특성 할당을 `LOGFONT` 구조입니다.|
|[CFontDialog::GetFaceName](#getfacename)|선택한 글꼴의 글꼴 이름을 반환합니다.|
|[CFontDialog::GetSize](#getsize)|선택한 글꼴의 포인트 크기를 반환합니다.|
|[CFontDialog::GetStyleName](#getstylename)|선택한 글꼴의 스타일 이름을 반환합니다.|
|[CFontDialog::GetWeight](#getweight)|선택한 글꼴의 두께 반환합니다.|
|[CFontDialog::IsBold](#isbold)|굵은 글꼴 인지 여부를 결정 합니다.|
|[CFontDialog::IsItalic](#isitalic)|글꼴이 기울임꼴인지 여부를 결정 합니다.|
|[CFontDialog::IsStrikeOut](#isstrikeout)|글꼴 서식을 취소선으로 표시 되는지 여부를 결정 합니다.|
|[CFontDialog::IsUnderline](#isunderline)|글꼴에 밑줄이 있는지 여부를 결정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|사용자 지정 하는 데 사용 되는 구조를 `CFontDialog` 개체입니다.|

## <a name="remarks"></a>설명

`CFontDialog` 개체는 현재 시스템에 설치 된 글꼴 목록이 포함 된 대화 상자. 사용자 목록에서 특정 글꼴을 선택할 수 및 응용 프로그램이 선택 다시 보고 됩니다.

생성 하는 `CFontDialog` 개체, 제공 된 생성자를 사용 하거나 새 하위 클래스를 파생 및 사용자 고유의 사용자 지정 생성자를 사용 합니다.

한 번을 `CFontDialog` 생성 된 개체를 사용할 수 있습니다는 `m_cf` 값 또는 대화 상자에서 컨트롤의 상태를 초기화 하는 구조입니다. 합니다 [m_cf](#m_cf) 형식의 구조체가 [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta)합니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

대화 상자 개체의 컨트롤을 초기화 한 후 호출 하 여 `DoModal` 대화 상자를 표시 하 고 사용자가 글꼴을 선택 하도록 허용 하려면 멤버 함수입니다. `DoModal` 사용자 확인 (IDOK) 또는 취소 (IDCANCEL) 단추를 선택 하는지 여부를 반환 합니다.

하는 경우 `DoModal` IDOK 반환 중 하나를 사용할 수 있습니다 `CFontDialog`의 사용자가 입력 한 정보를 검색 하는 멤버 함수입니다.

Windows를 사용할 수 있습니다 [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) 함수 대화 상자를 초기화 하는 동안 오류가 발생 했는지 여부를 확인 하 고 오류에 자세히 알아보기. 이 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

`CFontDialog` COMMDLG 의존합니다. Windows 버전 3.1 이상 함께 제공 되는 DLL 파일입니다.

대화 상자를 사용자 지정 하려면 클래스를 파생 `CFontDialog`사용자 지정 대화 상자 템플릿을 제공 하 고 확장 된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵을 추가 합니다. 처리 되지 않은 메시지는 기본 클래스에 전달 되어야 합니다.

후크 함수를 사용자 지정 필요 하지 않습니다.

사용 하 여 대 한 자세한 내용은 `CFontDialog`를 참조 하세요 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="cfontdialog"></a>  CFontDialog::CFontDialog

`CFontDialog` 개체를 생성합니다.

```
CFontDialog(
    LPLOGFONT lplfInitial = NULL,
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,
    DWORD dwFlags = CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*plfInitial*<br/>
에 대 한 포인터를 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 일부 글꼴 특성을 설정할 수 있는 데이터 구조입니다.

*charFormat*<br/>
에 대 한 포인터를 [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) 데이터 구조에서 다양 한 글꼴 특성 설정 할 수 있는 컨트롤을 편집 합니다.

*dwFlags*<br/>
하나 이상의 글꼴 선택 플래그를 지정합니다. 비트 OR 연산자를 사용하여 하나 이상의 미리 설정된 값을 결합할 수 있습니다. `m_cf.Flag` 구조체 멤버를 수정하는 경우 기본 동작을 그대로 유지하려면 변경에서 비트 OR 연산자를 사용해야 합니다. 이러한 플래그에 대 한 내용은 설명을 참조 합니다 [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) Windows SDK에는 구조입니다.

*pdcPrinter*<br/>
프린터 장치 컨텍스트에 대한 포인터입니다. 제공하는 경우 이 매개 변수는 글꼴을 선택할 프린터에 대한 프린터 장치 컨텍스트를 가리킵니다.

*pParentWnd*<br/>
글꼴 대화 상자의 부모 또는 소유자 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

생성자는 `CHOOSEFONT` 구조의 멤버를 자동으로 채웁니다. 기본값과는 다른 글꼴 대화 상자를 사용하려는 경우에만 이러한 멤버를 변경해야 합니다.

> [!NOTE]
>  rich edit 컨트롤이 지원되지 않는 경우에만 이 함수의 첫 번째 버전이 제공됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

##  <a name="domodal"></a>  CFontDialog::DoModal

Windows 일반 글꼴 대화 상자를 표시 하 고 사용자가 글꼴을 선택할 수 있도록 하려면이 함수를 호출 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

IDOK 또는 idcancel이 반환 됩니다. IDCANCEL이 반환 되는 Windows를 호출 [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) 오류가 발생 했는지 여부를 결정 하는 함수입니다.

IDOK 및 IDCANCEL는 사용자 확인 또는 취소 단추를 선택 하는지 여부를 나타내는 상수입니다.

### <a name="remarks"></a>설명

멤버를 설정 하 여 다양 한 글꼴 대화 상자 컨트롤을 초기화 하려는 경우는 [m_cf](#m_cf) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체에서 생성 된 후 있지만.

경우 `DoModal` IDOK 반환 함수를 설정 또는 사용자가 정보 입력 대화 상자에 검색할 다른 멤버를 호출할 수 있습니다.

### <a name="example"></a>예제

  에 대 한 예제를 참조 하세요 [CFontDialog::CFontDialog](#cfontdialog) 하 고 [CFontDialog::GetColor](#getcolor)합니다.

##  <a name="getcharformat"></a>  CFontDialog::GetCharFormat

선택한 글꼴의 문자 형식을 검색 합니다.

```
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>매개 변수

*cf*<br/>
A [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) 선택한 글꼴의 문자 서식 지정에 대 한 정보를 포함 하는 구조체.

##  <a name="getcolor"></a>  CFontDialog::GetColor

선택한 글꼴 색을 검색 하려면이 함수를 호출 합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴의 색입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

##  <a name="getcurrentfont"></a>  CFontDialog::GetCurrentFont

현재 선택한 글꼴의 특성의 멤버에 할당 하려면이 함수 호출을 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 구조입니다.

```
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>매개 변수

*lplf*<br/>
에 대 한 포인터를 `LOGFONT` 구조입니다.

### <a name="remarks"></a>설명

다른 `CFontDialog` 현재 글꼴의 개별 특성에 액세스 하려면 멤버 함수가 제공 됩니다.

호출 하는 동안이 함수를 호출 하는 경우 [DoModal](#domodal), 반환 시 현재 선택 영역 (사용자에 게 표시 하거나이 대화 상자에서 변경). 호출한 후이 함수를 호출 하는 경우 `DoModal` (경우에만 `DoModal` IDOK 반환), 실제로 선택한 사용자를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

##  <a name="getfacename"></a>  CFontDialog::GetFaceName

선택한 글꼴의 글꼴 이름을 검색 하려면이 함수를 호출 합니다.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴의 글꼴 이름을 `CFontDialog` 대화 상자.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

##  <a name="getsize"></a>  CFontDialog::GetSize

선택한 글꼴의 크기를 검색 하려면이 함수를 호출 합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>반환 값

글꼴의 크기는 포인트의 10 배로입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

##  <a name="getstylename"></a>  CFontDialog::GetStyleName

선택한 글꼴의 스타일 이름을 검색 하려면이 함수를 호출 합니다.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>반환 값

글꼴의 스타일 이름입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

##  <a name="getweight"></a>  CFontDialog::GetWeight

선택한 글꼴의 가중치를 검색 하려면이 함수를 호출 합니다.

```
int GetWeight() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴의 가중치입니다.

### <a name="remarks"></a>설명

글꼴의 가중치에 자세한 내용은 참조 [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

##  <a name="isbold"></a>  CFontDialog::IsBold

선택한 글꼴이 굵은 글꼴 인지 확인 하려면이 함수를 호출 합니다.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴에 굵게 표시 된 특성, 그렇지 않으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

##  <a name="isitalic"></a>  CFontDialog::IsItalic

선택한 글꼴에 기울임꼴 인지 확인 하려면이 함수를 호출 합니다.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴에 기울임꼴 특징이, 그렇지 않으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

##  <a name="isstrikeout"></a>  CFontDialog::IsStrikeOut

선택한 글꼴 서식을 취소선으로 표시 되는지 확인 하려면이 함수를 호출 합니다.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴에 취소선 특징이, 그렇지 않으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

##  <a name="isunderline"></a>  CFontDialog::IsUnderline

선택한 글꼴에 밑줄이 경우를 결정 하는이 함수를 호출 합니다.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴 않으면 밑줄 특징이 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

##  <a name="m_cf"></a>  CFontDialog::m_cf

멤버가 대화 상자 개체의 특성을 저장 하는 구조체입니다.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>설명

생성 한 후는 `CFontDialog` 개체를 사용할 수 있습니다 `m_cf` 호출 하기 전에 대화 상자의 다양 한 측면을 수정 하는 `DoModal` 멤버 함수입니다. 이 구조에 대 한 자세한 내용은 참조 하세요. [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>참고자료

[MFC Sample HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
