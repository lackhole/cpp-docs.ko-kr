---
title: CMFCToolBarFontSizeComboBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: 43832f6c9b02c43fbe4a05cbea3add8783150113
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767667"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox 클래스

사용자가 글꼴 크기를 선택할 수 있는 콤보 상자 컨트롤을 포함 하는 도구 모음 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|`CMFCToolBarFontSizeComboBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|선택한 글꼴 크기를 트윕 단위로 반환 합니다.|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|지정한 글꼴에 대 한 모든 지원 되는 글꼴 크기를 사용 하 여 콤보 상자 목록을 채웁니다.|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|트윕으로 글꼴 크기를 설정 합니다.|

## <a name="remarks"></a>설명

사용할 수는 `CMFCToolBarFontSizeComboBox` 와 함께 개체를 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 개체를 사용 하는 사용자가 글꼴 및 글꼴 크기를 선택할 수 있습니다.

글꼴 콤보 상자 단추를 추가 하는 것 처럼 도구 모음에는 글꼴 크기 콤보 상자 단추를 추가할 수 있습니다. 자세한 내용은 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)합니다.

사용자의 새 글꼴을 선택 하는 경우는 `CMFCToolBarFontComboBox` 개체를 사용 하 여 해당 글꼴에 대해 지원 되는 크기와 글꼴 크기 콤보 상자를 채울 수 있습니다 합니다 [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) 메서드.

## <a name="example"></a>예제

다음 예제에서 다양 한 메서드를 사용 하는 방법에 설명 합니다 `CMFCToolBarFontSizeComboBox` 구성 하는 클래스를 `CMFCToolBarFontSizeComboBox` 개체입니다. 이 예제에서는 텍스트 상자에서 글꼴 크기를 트윕 단위로 검색 모든 유효한 크기 지정 된 글꼴의 글꼴 크기 콤보 상자를 입력 하 고, 글꼴 크기를 트윕 단위로 지정 하는 방법을 보여 줍니다. 이 코드 조각은 [워드 패드 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarfontcombobox.h

##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

`CMFCToolBarFontSizeComboBox` 개체를 생성합니다.

```
CMFCToolBarFontSizeComboBox();
```

##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize

글꼴 크기 콤보 상자의 텍스트 상자에서 글꼴 크기를 트윕 단위로 검색합니다.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>반환 값

반환 값이 양수 이면에 트윕으로 글꼴 크기입니다. 콤보 상자의 텍스트 상자가 비어 있으면-1 것입니다. 오류가 발생 하는 경우-2입니다.

##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes

모든 유효한 크기 지정 된 글꼴의 글꼴 크기 콤보 상자를 채웁니다.

```
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>매개 변수

*strFontName*<br/>
[in] 글꼴 이름을 지정합니다.

### <a name="remarks"></a>설명

글꼴 콤보 상자에서 선택 및 글꼴 크기 콤보 상자와 같은 동기화 하려는 경우이 함수 호출을 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)합니다.

##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize

지정된 된 반올림 크기 트윕 단위로 지점과 다음 집합에서 가장 가까운 크기로 값 콤보 상자에서 선택한 크기입니다.

```
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
[in] 설정 하도록 트윕 단위로 글꼴 크기를 지정 합니다.

### <a name="remarks"></a>설명

호출 하 여 나중에 이전 유효한 글꼴 크기를 검색할 수 있습니다 합니다 [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) 메서드.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton 클래스](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo 클래스](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)
