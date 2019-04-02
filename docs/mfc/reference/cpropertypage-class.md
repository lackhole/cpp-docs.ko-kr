---
title: CPropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
ms.openlocfilehash: 9d4100037c5a6cd2eeef1a50fb2d5a46b2cb6505
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772725"
---
# <a name="cpropertypage-class"></a>CPropertyPage 클래스

속성 시트(탭 대화 상자라고도 함)의 개별 페이지를 나타냅니다.

## <a name="syntax"></a>구문

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPropertyPage::CPropertyPage](#cpropertypage)|`CPropertyPage` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPropertyPage::CancelToClose](#canceltoclose)|확인 단추 닫기, 읽을 수를 변경 하 고 모달 속성 시트의 페이지에서 복구할 수 없는 변경 이후 취소 단추를 사용 하지 않도록 설정 합니다.|
|[CPropertyPage::Construct](#construct)|`CPropertyPage` 개체를 생성합니다. 사용 하 여 `Construct` 런타임에 매개 변수를 지정 하려는 경우 또는 배열을 사용 하는 경우.|
|[CPropertyPage::GetPSP](#getpsp)|Windows 검색 [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2) 와 연결 된 구조는 `CPropertyPage` 개체입니다.|
|[CPropertyPage::OnApply](#onapply)|지금 적용 단추를 클릭할 때 프레임 워크에서 호출 합니다.|
|[CPropertyPage::OnCancel](#oncancel)|취소 단추를 클릭할 때 프레임 워크에서 호출 합니다.|
|[CPropertyPage::OnKillActive](#onkillactive)|현재 페이지가 더 이상 활성 페이지가 있을 때 프레임 워크에서 호출 됩니다. 여기에 데이터 유효성 검사를 수행 합니다.|
|[CPropertyPage::OnOK](#onok)|확인, 지금 적용 또는 [닫기] 단추를 클릭할 때 프레임 워크에서 호출 합니다.|
|[CPropertyPage::OnQueryCancel](#onquerycancel)|취소 단추를 클릭할 때와 취소 작업이 수행 되기 전에 프레임 워크에서 호출 됩니다.|
|[CPropertyPage::OnReset](#onreset)|취소 단추를 클릭할 때 프레임 워크에서 호출 합니다.|
|[CPropertyPage::OnSetActive](#onsetactive)|페이지에는 활성 페이지가 만들어질 때 프레임 워크에서 호출 됩니다.|
|[CPropertyPage::OnWizardBack](#onwizardback)|마법사 형식의 속성 시트를 사용 하는 동안 뒤로 단추를 클릭할 때 프레임 워크에서 호출 합니다.|
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|마법사 형식의 속성 시트를 사용 하는 동안 "마침" 단추를 클릭할 때 프레임 워크에서 호출 합니다.|
|[CPropertyPage::OnWizardNext](#onwizardnext)|마법사 형식의 속성 시트를 사용 하는 동안 다음 단추를 클릭할 때 프레임 워크에서 호출 합니다.|
|[CPropertyPage::QuerySiblings](#querysiblings)|속성 시트의 각 페이지에 메시지를 전달합니다.|
|[CPropertyPage::SetModified](#setmodified)|지금 적용 단추를 비활성화 또는 활성화를 호출 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2) 구조입니다. 기본 속성 페이지 매개 변수에 대 한 액세스를 제공합니다.|

## <a name="remarks"></a>설명

표준 대화 상자를 사용 하 여에서 클래스를 파생 하는 대로 `CPropertyPage` 속성 시트의 각 페이지에 대 한 합니다. 사용 하도록 `CPropertyPage`-파생된 개체를 먼저 만들어야 합니다.는 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) 개체를 만든 후 속성 시트에서 이동 하는 각 페이지에 대 한 개체입니다. 호출 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) 각 시트에 페이지 및 호출 하 여 속성 시트를 표시 한 다음 [CPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 모달 속성 시트를 보려면 또는 [CPropertySheet:: 만들](../../mfc/reference/cpropertysheet-class.md#create) 모덜리스 속성 시트에 대 한 합니다.

속성 시트를 사용자에 게는 뉴스레터를 만들거나 장치를 설정 하는 등 작업의 단계를 안내 하는 속성 페이지의 시퀀스를 사용 하 여 구성 마법사 라는 탭 대화 상자의 형식을 만들 수 있습니다. 마법사 형식의 탭 대화 상자에 속성 페이지 탭 없는 및 한 번에 하나의 속성 페이지가 표시 됩니다. 또한 확인 및 지금 적용 단추 대신 마법사 종류 탭 대화 상자에 뒤로 단추, 다음 또는 완료 단추 및 취소 단추

속성 시트를 설정 하는 마법사에 대 한 자세한 내용은 참조 하세요. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다. 사용 하 여 대 한 자세한 내용은 `CPropertyPage` 문서를 참조 하는 개체를 [속성 시트 및 속성 페이지](../../mfc/property-sheets-and-property-pages-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="canceltoclose"></a>  CPropertyPage::CancelToClose

모달 속성 시트 페이지에 데이터를 복구할 수 없는 변경 수행 된 후이 함수를 호출 합니다.

```
void CancelToClose();
```

### <a name="remarks"></a>설명

이 함수 close 확인 단추를 변경 하 고 취소 단추를 사용 하지 않도록 설정 합니다. 이 변경 경고 변경은 영구, 수정, 사용자를 취소할 수 없습니다.

`CancelToClose` 모덜리스 속성 시트에 없기 때문에 취소 단추가 기본적으로 멤버 함수는 모덜리스 속성 시트에 아무 작업도 수행 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertyPage::QuerySiblings](#querysiblings)합니다.

##  <a name="construct"></a>  CPropertyPage::Construct

생성 하려면이 멤버 함수 호출을 `CPropertyPage` 개체입니다.

```
void Construct(
    UINT nIDTemplate,
    UINT nIDCaption = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0);

void Construct(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
이 페이지에 사용 되는 템플릿의 ID입니다.

*nIDCaption*<br/>
이 페이지의 탭에 배치할 ID 이름입니다. 0 인 경우이 페이지에 대 한 대화 상자 템플릿에서 이름 수행 됩니다.

*lpszTemplateName*<br/>
템플릿 리소스의 이름을 나타내는 null로 끝나는 문자열을 포함 합니다.

*nIDHeaderTitle*<br/>
속성 페이지 머리글의 제목 위치에 배치할 ID 이름입니다. 기본적으로 0입니다.

*nIDHeaderSubTitle*<br/>
속성 페이지 머리글의 부제목 위치에 배치할 ID 이름입니다. 기본적으로 0입니다.

### <a name="remarks"></a>설명

개체는 다음 조건이 모두 충족 되 면 표시 됩니다.

- 페이지를 사용 하 여 속성 시트에 추가 되었습니다 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)합니다.

- 속성 시트 [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 하거나 [만들기](../../mfc/reference/cpropertysheet-class.md#create) 함수가 호출 되었습니다.

- 사용자가 선택한 (탭)이이 페이지입니다.

호출 `Construct` 중 다른 클래스 생성자 호출 되지 않은 경우. `Construct` 멤버 함수 이므로 유연한 문에 매개 변수를 비워 둡니다 하 고 다음 코드에서 여러 매개 변수 및 생성 시점을 지정할 수 있습니다.

사용 해야 합니다 `Construct` 배열을 사용 하 여 작업할 시점과 호출 해야 `Construct` 배열의 각 멤버에 대 한 데이터 멤버를 적절 한 값이 할당 됩니다 있도록 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage

`CPropertyPage` 개체를 생성합니다.

```
CPropertyPage();

explicit CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

explicit CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
이 페이지에 사용 되는 템플릿의 ID입니다.

*nIDCaption*<br/>
이 페이지의 탭에 배치할 ID 이름입니다. 0 인 경우이 페이지에 대 한 대화 상자 템플릿에서 이름 수행 됩니다.

*dwSize*<br/>
*lpszTemplateName* 이 페이지에 대 한 서식 파일의 이름을 포함 하는 문자열을 가리킵니다. NULL일 수 없습니다.

*nIDHeaderTitle*<br/>
속성 페이지 머리글의 제목 위치에 배치할 ID 이름입니다.

*nIDHeaderSubTitle*<br/>
속성 페이지 머리글의 부제목 위치에 배치할 ID 이름입니다.

### <a name="remarks"></a>설명

개체는 다음 조건이 모두 충족 되 면 표시 됩니다.

- 페이지를 사용 하 여 속성 시트에 추가 되었습니다 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)합니다.

- 속성 시트 [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 하거나 [만들기](../../mfc/reference/cpropertysheet-class.md#create) 함수가 호출 되었습니다.

- 사용자가 선택한 (탭)이이 페이지입니다.

사용 하 여 여러 매개 변수 (예: 배열을 사용 하는 경우)에 있으면 [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) 대신 `CPropertyPage`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

##  <a name="getpsp"></a>  CPropertyPage::GetPSP

Windows 검색 [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2) 와 연결 된 구조는 `CPropertyPage` 개체입니다.

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>반환 값

에 대 한 참조를 `PROPSHEETPAGE` 구조입니다.

##  <a name="m_psp"></a>  CPropertyPage::m_psp

`m_psp` 해당 멤버의 특성을 저장 하는 구조 [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2)합니다.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>설명

이 구조를 사용 하 여 생성 된 후 속성 페이지의 모양을 초기화 합니다.

해당 멤버의 목록을 포함 하 여이 구조에 대 한 자세한 내용은 참조 `PROPSHEETPAGE` Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

##  <a name="onapply"></a>  CPropertyPage::OnApply

이 멤버 함수를 확인 또는 지금 적용 단추를 선택 하면 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>반환 값

변경 내용을 허용 되는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

프레임 워크에서이 함수를 호출 하면 속성 시트의 모든 속성 페이지에 대 한 변경 내용을 수용할 속성 시트에 포커스를 유지 하 고 `OnApply` (값 1) TRUE를 반환 합니다. 하기 전에 `OnApply` 호출할 수 있습니다, 프레임 워크에서 호출 했어야 합니다 [SetModified](#setmodified) 해당 매개 변수를 TRUE로 설정 합니다. 이 사용자 속성 페이지에서 변경의 작업을 수행 하는 즉시 지금 적용 단추를 활성화 합니다.

프로그램은 사용자가 지금 적용 단추를 클릭 하면 동작을 지정 하려면이 멤버 함수를 재정의 합니다. 를 재정의할 때 함수 변경 사항을 적용 하려면 TRUE이 고 변경 내용을 적용 하지 않도록 설정 하려면 FALSE를 반환 해야 합니다.

기본 구현의 `OnApply` 호출 `OnOK`합니다.

사용자가 속성 시트에서 지금 적용을 확인 단추를 누를 때 전송 되는 알림 메시지에 대 한 자세한 내용은 참조 하세요. [PSN_APPLY](/windows/desktop/Controls/psn-apply) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertyPage::OnOK](#onok)합니다.

##  <a name="oncancel"></a>  CPropertyPage::OnCancel

이 멤버 함수는 취소 단추를 선택 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnCancel();
```

### <a name="remarks"></a>설명

취소 단추 작업을 수행 하려면이 멤버 함수를 재정의 합니다. 기본값 적용 된 변경 내용을 부정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive

이 멤버 함수는 페이지가 더 이상 활성 페이지가 있을 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>반환 값

데이터를 성공적으로 업데이트 된 경우 0이 아닌 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

특별 한 데이터 유효성 검사 작업을 수행 하려면이 멤버 함수를 재정의 합니다.

이 멤버 함수의 기본 구현은 속성 페이지에 있는 컨트롤에서 속성 페이지의 멤버 변수 설정을 복사합니다. 대화 상자 데이터 유효성 검사 (DDV) 오류로 인해 데이터를 성공적으로 업데이트 되지 않았습니다 하는 경우 페이지에 포커스가 유지 됩니다.

이 멤버 함수는 성공적으로 반환 된 후 페이지의 호출 됩니다 [OnOK](#onok) 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

##  <a name="onok"></a>  CPropertyPage::OnOK

이 멤버 함수는 프레임 워크 호출 바로 다음을 확인 하거나 지금 적용 단추를 선택 하면 프레임 워크에서 호출 됩니다 [OnKillActive](#onkillactive)합니다.

```
virtual void OnOK();
```

### <a name="remarks"></a>설명

확인 하거나 지금 적용 단추를 선택 하면 프레임 워크를 수신 합니다 [PSN_APPLY](/windows/desktop/Controls/psn-apply) 속성 페이지에서 알림. 에 대 한 호출 `OnOK` 호출 하는 경우에 만들 수 없습니다 [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) 속성 페이지 알림을 보내지 않습니다 경우 때문입니다.

사용자가 전체 속성 시트를 닫을 때 현재 페이지에 맞는 추가 동작을 구현 하려면이 멤버 함수를 재정의 합니다.

이 멤버 함수를 기본 구현에는 페이지는 데이터에서 업데이트를 반영 하도록 "정리" 표시를 `OnKillActive` 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel

이 멤버 함수는 사용자가 취소 단추를 클릭 하 고 취소 하기 전에 작업을 수행한 경우 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>반환 값

취소 작업을 방지 하기 위해 FALSE 또는 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

프로그램은 사용자가 취소 단추를 클릭할 때 작업을 지정 하려면이 멤버 함수를 재정의 합니다.

기본 구현을 `OnQueryCancel` TRUE를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

##  <a name="onreset"></a>  CPropertyPage::OnReset

이 멤버 함수는 사용자가 취소 단추를 선택 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnReset();
```

### <a name="remarks"></a>설명

프레임 워크에서이 함수를 호출 하면 이전에 지금 적용 단추를 선택 하는 사용자가 수행한 모든 속성 페이지에 변경 내용을 무시 되 고 속성 시트 포커스를 유지 합니다.

프로그램은 사용자가 취소 단추를 클릭할 때 동작을 지정 하려면이 멤버 함수를 재정의 합니다.

기본 구현을 `OnReset` 아무 작업도 수행 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertyPage::OnCancel](#oncancel)합니다.

##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive

이 멤버 함수는 페이지는 사용자가 선택 되 고 활성 페이지가 됩니다 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>반환 값

페이지를 성공적으로 활성; 설정 되었으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

페이지가 활성화 될 때 작업을 수행 하려면이 멤버 함수를 재정의 합니다. 일반적으로이 멤버 함수 재정의 페이지 컨트롤을 새 데이터로 업데이트 수 있도록 데이터 멤버를 업데이트 한 후 기본 버전을 호출 됩니다.

기본 구현은 페이지에 대 한 창을 만듭니다. 그렇지 않은 경우 이전에 만든를 활성 페이지를 사용 하면 됩니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext)합니다.

##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack

이 멤버 함수는 사용자가 마법사에서 뒤로 단추를 클릭할 때 프레임 워크에서 호출 됩니다.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>반환 값

다음 페이지를 자동으로 이동 하는 0 페이지 변경 하지 않으려면-1입니다. 다음 이외의 페이지로 이동할 표시할 대화의 식별자를 반환 합니다.

### <a name="remarks"></a>설명

사용자는 뒤로 단추를 누를 때 수행 해야 하는 일부 작업을 지정 하려면이 멤버 함수를 재정의 합니다.

마법사 형식의 속성 시트를 확인 하는 방법에 대 한 자세한 내용은 참조 하세요. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish

이 멤버 함수는 사용자가 마법사에서 마침 단추를 클릭할 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>반환 값

마법사를 완료; 속성 시트 제거 될 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

클릭할 때 합니다 **완료** 이 함수를 호출 하는 프레임 워크는 마법사의 단추는 경우 `OnWizardFinish` 제거할 수 있습니다 (하지만 실제로 제거 되지 않습니다) TRUE (0이 아닌 값) 속성 시트를 반환 합니다. 호출 `DestroyWindow` 속성 시트를 삭제 하려면. 호출 하지 마세요 `DestroyWindow` 에서 `OnWizardFinish`; 그렇게 하면 힙 손상 또는 기타 오류입니다.

사용자는 "마침" 단추를 누를 때 수행 해야 하는 일부 작업을 지정 하려면이 멤버 함수를 재정의할 수 있습니다. 이 함수를 재정의할 때 소멸 되는 속성 시트를 방지 하려면 FALSE를 반환 합니다.

사용자가 마법사 속성 시트에서 "마침" 단추를 누를 때 전송 되는 알림 메시지에 대 한 자세한 내용은 참조 하세요. [PSN_WIZFINISH](/windows/desktop/Controls/psn-wizfinish) Windows SDK에 있습니다.

마법사 형식의 속성 시트를 확인 하는 방법에 대 한 자세한 내용은 참조 하세요. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext

이 멤버 함수는 사용자가 마법사에서 다음 단추를 클릭할 때 프레임 워크에서 호출 됩니다.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>반환 값

다음 페이지를 자동으로 이동 하는 0 페이지 변경 하지 않으려면-1입니다. 다음 이외의 페이지로 이동할 표시할 대화의 식별자를 반환 합니다.

### <a name="remarks"></a>설명

다음 단추를 누를 때 수행 되어야 하는 일부 작업을 지정 하려면이 멤버 함수를 재정의 합니다.

마법사 형식의 속성 시트를 확인 하는 방법에 대 한 자세한 내용은 참조 하세요. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings

속성 시트의 각 페이지에 메시지를 전달 하려면이 멤버 함수를 호출 합니다.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*wParam*<br/>
추가 메시지 종속 정보를 지정 합니다.

*lParam*<br/>
추가 메시지 종속 정보를 지정합니다.

### <a name="return-value"></a>반환 값

속성 시트 또는 0 이면 페이지에서 0이 아닌 값을 모든 페이지 값이 0 반환합니다.

### <a name="remarks"></a>설명

속성 시트는 페이지 0이 아닌 값을 반환 하는 경우 후속 페이지에 메시지를 보내지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

##  <a name="setmodified"></a>  CPropertyPage::SetModified

사용 하도록 설정 하거나 지금 적용 단추를 적절 한 외부 개체에 속성 페이지에서 설정을 적용 여부에 따라 사용 하지 않도록 하려면이 멤버 함수를 호출 합니다.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>매개 변수

*bChanged*<br/>
속성 페이지 설정; 적용 된 마지막 시간 이후 수정 된 것을 나타내려면 TRUE 속성 페이지 설정 적용 된 하거나 무시할지 FALSE입니다.

### <a name="remarks"></a>설명

프레임 워크는 추적 페이지에 "더티" 즉, 속성 페이지를 호출한 `SetModified( TRUE )`합니다. 지금 적용 단추를 호출 하는 경우에 항상 사용할 수 `SetModified( TRUE )` 페이지 중 하나에 대 한 합니다. 호출 하는 경우 지금 적용 단추가 비활성화 됩니다 `SetModified( FALSE )` 단 하는 경우 다른 페이지 없음 ". 더티" 페이지 중 하나에 대 한

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CDialog 클래스](../../mfc/reference/cdialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet 클래스](../../mfc/reference/cpropertysheet-class.md)<br/>
[CDialog 클래스](../../mfc/reference/cdialog-class.md)
