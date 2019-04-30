---
title: CMFCRibbonSeparator 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
ms.openlocfilehash: 4806582a226590459a104f64499ab6ae541570e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380236"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator 클래스

리본 구분 기호를 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|`CMFCRibbonSeparator` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|구분 기호를 추가 합니다 **명령** 목록에 **사용자 지정** 대화 상자. (재정의 [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|
|`CMFCRibbonSeparator::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonSeparator::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|

### <a name="protected-methods"></a>Protected 메서드

|||
|-|-|
|이름|설명|
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|다른 개체에서 구분 기호의 멤버 변수를 설정 하는 복사 메서드.|
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|구분 기호의 크기를 반환합니다.|
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|구분 기호 인지 여부를 나타냅니다.|
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|탭 정지 인지 여부를 나타냅니다.|
|[CMFCRibbonSeparator::OnDraw](#ondraw)|리본 메뉴 또는 빠른 실행 도구 모음에서 구분 기호를 그리기 위해 시스템에서 호출 됩니다.|
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|구분 기호에 그릴 시스템에 의해 호출 된 **명령** 목록입니다.|

## <a name="remarks"></a>설명

리본 구분 기호는 세로 또는 가로 줄이는 논리적으로 분리 리본 요소입니다. 리본 컨트롤을 기본 응용 프로그램 메뉴와 리본 상태 표시줄, 빠른 실행 도구 모음에 구분선을 그릴 수 있습니다.

응용 프로그램에서 구분 기호를 사용 하려면 새 개체를 생성 하 고 다음과 같이 기본 응용 프로그램 메뉴에 추가 합니다.

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```
호출 [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) 리본 패널에 구분 기호를 추가 합니다. 구분 기호에 할당 되 고 내부적으로 추가 된 `AddSeparator` 메서드.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxbaseribbonelement.h

##  <a name="addtolistbox"></a>  CMFCRibbonSeparator::AddToListBox

구분 기호를 추가 합니다 **명령** 목록에 **사용자 지정** 대화 상자.

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>매개 변수

*pWndListBox*<br/>
[in] 에 대 한 포인터를 **명령** 목록 구분 기호를 추가 하는 위치입니다.

*bDeep*<br/>
[in] Ignored.

### <a name="return-value"></a>반환 값

0부터 시작 하 여 지정 된 목록 상자에서 문자열 인덱스 *pWndListBox*합니다.

##  <a name="cmfcribbonseparator"></a>  CMFCRibbonSeparator::CMFCRibbonSeparator

`CMFCRibbonSeparator` 개체를 생성합니다.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>매개 변수

*bIsHoriz*<br/>
[in] 구분 기호는 가로; TRUE 인 경우 FALSE 인 경우에 구분 기호는 세로입니다.

### <a name="remarks"></a>설명

가로 구분 기호는 응용 프로그램 메뉴에 사용 됩니다. 세로 구분 기호는 도구 모음에 사용 됩니다.

### <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCRibbonSeparator` 클래스입니다.

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCRibbonSeparator::CopyFrom

다른 개체에서 구분 기호의 멤버 변수를 설정 하는 복사 메서드.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>매개 변수

*Src*<br/>
[in] 복사할 소스 리본 요소입니다.

##  <a name="getregularsize"></a>  CMFCRibbonSeparator::GetRegularSize

구분 기호의 크기를 반환합니다.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 내용에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

크기 지정 된 디바이스 컨텍스트 구분 기호입니다.

##  <a name="isseparator"></a>  CMFCRibbonSeparator::IsSeparator

구분 기호 인지 여부를 나타냅니다.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>반환 값

이 클래스에 대해 항상 TRUE입니다.

##  <a name="istabstop"></a>  CMFCRibbonSeparator::IsTabStop

탭 정지 인지 여부를 나타냅니다.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>반환 값

이 클래스에 대해 항상 FALSE입니다.

### <a name="remarks"></a>설명

구분 기호를 리본 탭은 아닙니다.

##  <a name="ondraw"></a>  CMFCRibbonSeparator::OnDraw

리본 메뉴 또는 빠른 실행 도구 모음에서 구분 기호를 그리기 위해 시스템에서 호출 됩니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

##  <a name="ondrawonlist"></a>  CMFCRibbonSeparator::OnDrawOnList

구분 기호에 그릴 시스템에 의해 호출 된 **명령** 목록입니다.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDC*|[in] 장치 컨텍스트에 대 한 포인터입니다.|
|*strText*|[in] 목록에 표시할 텍스트입니다.|
|*nTextOffset*|[in] 텍스트 및 경계 사각형의 왼쪽 사이의 간격입니다.|
|*rect*|[in] 경계 사각형을 지정합니다.|
|*bIsSelected*|[in] Ignored.|
|*bHighlighted*|[in] Ignored.|

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
