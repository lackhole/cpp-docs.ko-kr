---
title: CMFCRibbonCheckBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
ms.openlocfilehash: 34af1ae818125abd51b9eaf04cd98f9ac24addb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392546"
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox 클래스

`CMFCRibbonCheckBox` 클래스는 리본 패널, 빠른 실행 도구 모음 또는 팝업 메뉴에 추가할 수 있는 확인란을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(재정의 [cmfcribbonbutton:: Getcompactsize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(재정의 [cmfcribbonbutton:: Getintermediatesize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(재정의 [cmfcribbonbutton:: Getregularsize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|( `CMFCRibbonButton::IsDrawTooltipImage`을 재정의합니다.)|
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(재정의 [cmfcribbonbutton:: Ondraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(재정의 [cmfcribbonbaseelement:: Ondrawmenuimage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|( `CMFCRibbonButton::OnDrawOnList`을 재정의합니다.)|
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(재정의 [cmfcribbonbutton:: Setaccdata](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

## <a name="remarks"></a>설명

애플리케이션에서 `CMFCRibbonCheckBox`를 사용하려면 코드에 다음 생성자를 추가합니다.

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```
여기서 *nID* 는 확인란 명령 ID 및 *lpszText* 확인란의 텍스트 레이블입니다.

사용 하 여 리본 패널에 확인란을 추가할 수 있습니다 [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribboncheckbox.h

##  <a name="cmfcribboncheckbox"></a>  CMFCRibbonCheckBox::CMFCRibbonCheckBox

리본 확인란 개체의 생성자

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 명령 ID를 지정 합니다.

*lpszText*<br/>
[in] 텍스트 레이블을 지정합니다.

### <a name="return-value"></a>반환 값

리본 확인란 개체를 생성합니다.

### <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCRibbonCheckBox` 클래스입니다.

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

##  <a name="getcompactsize"></a>  CMFCRibbonCheckBox::GetCompactSize

재정의 된 경우 확인란의 압축 크기를 가져옵니다.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 확인란을 사용 하 여 연결 된 CDC에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 된 `CSize` 확인란의 압축 크기를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

재정의 되지 않으면 확인란의 중간 크기를 반환 합니다.

##  <a name="getintermediatesize"></a>  CMFCRibbonCheckBox::GetIntermediateSize

확인란의 중간 크기를 가져옵니다.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 이 확인란을 사용 하 여 연결 된 CDC에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

`CSize` 확인란의 중간 크기를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

재정의 되지 않으면 기본 확인란 크기로 중간 크기를 계산 ( `AFX_CHECK_BOX_DEFAULT_SIZE`) 및 텍스트 크기와 여백입니다.

##  <a name="getregularsize"></a>  CMFCRibbonCheckBox::GetRegularSize

확인란의 일반 크기를 가져옵니다.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 이 확인란을 사용 하 여 연결 된 CDC 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 된 `CSize` 확인란의 보통 크기를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

재정의 되지 않으면 확인란의 중간 크기를 반환 합니다.

##  <a name="isdrawtooltipimage"></a>  CMFCRibbonCheckBox::IsDrawTooltipImage

확인란을 사용 하 여 연결 하는 도구 설명 이미지 인지 여부를 나타냅니다.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>반환 값

확인란을 사용 하 여 연결 또는 그렇지 않은 경우 FALSE를 도구 설명 이미지 이면 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

##  <a name="ondraw"></a>  CMFCRibbonCheckBox::OnDraw

지정 된 디바이스 컨텍스트를 사용 하 여 확인란을 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 확인란을 그릴 CDC에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="ondrawmenuimage"></a>  CMFCRibbonCheckBox::OnDrawMenuImage

확인란에 대 한 메뉴 이미지를 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>매개 변수

[in] *CDC&#42;*<br/>
확인란을 사용 하 여 연결 된 CDC에 대 한 포인터입니다.

*CRect*<br/>
[in] `CRect` 메뉴 이미지를 그릴 사각형을 지정 하는 개체입니다.

### <a name="return-value"></a>반환 값

이미지를 그릴 경우 TRUE 또는 그렇지 않은 경우 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

재정의 되지 않으면 FALSE를 반환 합니다.

##  <a name="ondrawonlist"></a>  CMFCRibbonCheckBox::OnDrawOnList

명령 목록 상자에서 확인란을 그리기 위해 프레임 워크에서 호출 됩니다.

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

*pDC*<br/>
[in] 확인란을 그릴 장치 컨텍스트에 대 한 포인터입니다.

*strText*<br/>
[in] 표시 텍스트입니다.

*nTextOffset*<br/>
[in] 텍스트를 표시할 목록 상자의 왼쪽에서의 픽셀 단위의 거리입니다.

*rect*<br/>
[in] 확인란의 표시 사각형을 합니다.

*bIsSelected*<br/>
[in] 확인란을 선택 하거나 그렇지 않은 경우 FALSE 이면 TRUE입니다.

*bHighlighted*<br/>
[in] 확인란 강조 표시 된, 또는 그렇지 않은 경우 FALSE 이면 TRUE입니다.

### <a name="remarks"></a>설명

##  <a name="setaccdata"></a>  CMFCRibbonCheckBox::SetACCData

확인란에 대 한 내게 필요한 옵션 데이터를 설정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
확인란의 부모 창입니다.

*data*<br/>
확인란에 대 한 내게 필요한 옵션 데이터입니다.

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

기본적으로이 메서드는 확인란에 대 한 내게 필요한 옵션 데이터를 설정 하 고 항상 TRUE를 반환 합니다. 내게 필요한 옵션 데이터를 설정하고 성공 또는 실패를 나타내는 값을 반환하려면 이 메서드를 재정의합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel 클래스](../../mfc/reference/cmfcribbonpanel-class.md)
