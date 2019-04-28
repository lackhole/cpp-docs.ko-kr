---
title: CMFCPropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: 62e33da998f1e5332436d887c38d3fd65526561b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310491"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage 클래스

`CMFCPropertyPage` 클래스 속성 페이지에서 팝업 메뉴의 표시를 지원 합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|`CMFCPropertyPage` 개체를 생성합니다.|
|`CMFCPropertyPage::~CMFCPropertyPage`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCPropertyPage::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|`CMFCPropertyPage::OnSetActive`|이 멤버 함수는 페이지는 사용자가 선택 되 고 활성 페이지가 됩니다 때 프레임 워크에서 호출 됩니다. (재정의 [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|디스패치 되기 전에 창 메시지를 변환 합니다 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 함수입니다. 자세한 내용 및 메서드 구문 참조 [cwnd:: Pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)합니다. ( `CPropertyPage::PreTranslateMessage`을 재정의합니다.)|

## <a name="remarks"></a>설명

`CMFCPropertyPage` 클래스 탭 대화 상자 라고도 하는 속성 시트의 개별 페이지를 나타냅니다.

사용 된 `CMFCPropertyPage` 와 함께 클래스를 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) 클래스. 메뉴에서 속성 페이지를 사용 하려면 모든 일치 항목을 바꾸려면 합니다 `CPropertyPage` 클래스는 `CMFCPropertyPage` 클래스입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertypage.h

##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage

`CMFCPropertyPage` 개체를 생성합니다.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
이 페이지에 대 한 템플릿의 리소스 ID입니다.

*nIDCaption*<br/>
이 페이지의 탭에 삽입할 레이블의 리소스 ID입니다. 0 인 경우이 페이지에 대 한 대화 상자 템플릿에에서 이름을 가져옵니다. 기본값은 0입니다.

*lpszTemplateName*<br/>
이 페이지에 대 한 템플릿의 이름 가리킵니다. NULL일 수 없습니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

생성자 매개 변수에 대 한 자세한 내용은 참조 하세요. [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet 클래스](../../mfc/reference/cmfcpropertysheet-class.md)
