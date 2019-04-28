---
title: CMFCRibbonCustomizePropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 8c790ca249f34a3c9b36d1bd77dafdc4a91bd352
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237053"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage 클래스

에 대 한 사용자 지정 페이지를 구현 합니다 **사용자 지정** 리본 메뉴 기반 응용 프로그램에서 대화 상자.

## <a name="syntax"></a>구문

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|`CMFCRibbonCustomizePropertyPage` 개체를 생성합니다.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|사용자 지정 범주를 추가 합니다 **명령** 콤보 상자입니다.|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|사용자가 클릭할 때 시스템에서 호출 **확인** 에 **사용자 지정** 대화 상자.|

## <a name="remarks"></a>설명

사용자 지정 명령을 추가 하려는 경우는 **사용자 지정** 대화 상자에서 AFX_WM_ON_RIBBON_CUSTOMIZE 메시지를 처리 해야 합니다. 메시지 처리기에서 인스턴스화하는 `CMFCRibbonCustomizePropertyPage` 스택의 개체입니다. 사용자 지정 명령 목록을 만들고 호출 `AddCustomCategory` 새 페이지를 추가 하는 **사용자 지정** 대화 상자.

## <a name="example"></a>예제

다음 예제에는 생성 하는 방법을 보여 줍니다.는 `CMFCRibbonCustomizePropertyPage` 개체 및 사용자 지정 범주를 추가할 수 있습니다.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribboncustomizedialog.h

##  <a name="addcustomcategory"></a>  CMFCRibbonCustomizePropertyPage::AddCustomCategory

사용자 지정 범주를 추가 합니다 **명령** 콤보 상자입니다.

```
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*lpszName*|[in] 사용자 지정 범주 이름을 지정합니다.|
|*lstIDS*|[in] 사용자 지정 범주에 표시 될 리본 메뉴 명령 Id를 포함 합니다.|

### <a name="remarks"></a>설명

이 메서드는 명명 된 범주를 추가 *lpszName* 에 **명령** 콤보 상자입니다. 명령에 지정 된 사용자가 범주를 선택 하면 *lstIDS* 명령 목록에 표시 합니다.

##  <a name="cmfcribboncustomizepropertypage"></a>  CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

`CMFCRibbonCustomizePropertyPage` 개체를 생성합니다.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>매개 변수

*pRibbonBar*<br/>
[in] 리본 컨트롤에 대 한 포인터를 사용자 지정 하는 옵션입니다.

##  <a name="onok"></a>  CMFCRibbonCustomizePropertyPage::OnOK

클릭할 때 시스템에서 Calleld **확인** 에 **사용자 지정** 대화 상자.

```
virtual void OnOK();
```

### <a name="remarks"></a>설명

기본 구현에서 선택한 옵션을 적용 합니다 **사용자 지정** 빠른 실행 도구 모음에 대화 상자.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
