---
title: CMFCRibbonFontComboBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
ms.openlocfilehash: 643e2a519c6d96c1070990dd86d571c5b7c09f95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237027"
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox 클래스

글꼴 목록이 포함된 콤보 상자를 구현합니다. 콤보 상자를 리본 패널에 배치합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|소멸자|

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|`CMFCRibbonFontComboBox` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|지정된 글꼴 종류, 문자 집합, 피치 및 패밀리의 글꼴로 리본 글꼴 콤보 상자를 채웁니다.|
|`CMFCRibbonFontComboBox::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|지정된 문자 집합을 반환합니다.|
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|콤보 상자에 표시할 글꼴 종류를 반환합니다. 유효한 옵션 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE 또는 이러한 옵션의 비트 조합입니다.|
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|콤보 상자에 표시되는 글꼴의 피치 및 패밀리를 반환합니다.|
|`CMFCRibbonFontComboBox::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|이전에 지정한 글꼴 종류, 문자 집합, 피치 및 패밀리의 글꼴로 리본 글꼴 콤보 상자를 채웁니다.|
|[CMFCRibbonFontComboBox::SetFont](#setfont)|콤보 상자에서 지정된 글꼴을 선택합니다.|

## <a name="remarks"></a>설명

만든 후에 `CMFCRibbonFontComboBox` 개체를 호출 하 여 리본 패널에 추가 [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonComboBox.h

##  <a name="buildfonts"></a>  CMFCRibbonFontComboBox::BuildFonts

글꼴을 사용 하 여 리본에서 콤보 상자를 채웁니다.

```
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>매개 변수

*nFontType*<br/>
[in] 추가할 글꼴의 글꼴 종류를 지정 합니다.

*nCharSet*<br/>
[in] 추가할 글꼴의 문자 집합을 지정 합니다.

*nPitchAndFamily*<br/>
[in] 피치 및 추가할 글꼴의 제품군을 지정 합니다.

##  <a name="cmfcribbonfontcombobox"></a>  CMFCRibbonFontComboBox::CMFCRibbonFontComboBox

생성 하 고 초기화 된 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) 개체입니다.

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 콤보 상자에서 항목을 선택할 때 실행 되는 명령의 명령 ID입니다.

*nFontType*<br/>
[in] 글꼴 콤보 상자에 표시할 형식을 지정 합니다. 유효한 옵션 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE 또는 이러한 옵션의 비트 조합입니다.

*nCharSet*<br/>
[in] 지정된 된 문자 집합에 속해 있는 콤보 상자에 있는 글꼴 필터링...

*nPitchAndFamily*<br/>
[in] 피치 및 콤보 상자에 표시 되는 글꼴의 제품군을 지정 합니다.

*nWidth*<br/>
[in] 콤보 상자의 픽셀 너비를 지정 합니다.

### <a name="remarks"></a>설명

가능한 대 한 자세한 내용은 *nFontType* 매개 변수 값을 참조 하십시오 [EnumFontFamProc](https://msdn.microsoft.com/library/windows/desktop/dd162621) Windows SDK 설명서의 합니다.

에 할당할 수 있는 유효한 문자 집합에 대 한 자세한 *nCharSet*, 및 할당할 수 있는 유효한 값 *nPitchAndFamily*를 참조 하세요 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 에 Windows SDK 설명서입니다.

##  <a name="getfontdesc"></a>  CMFCRibbonFontComboBox::GetFontDesc

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>매개 변수

[in] *iIndex*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="rebuildfonts"></a>  CMFCRibbonFontComboBox::RebuildFonts

이전에 지정한 글꼴 종류, 문자 집합 및 피치 및 패밀리 글꼴을 사용 하 여 리본에서 콤보 상자를 채웁니다.

```
void RebuildFonts();
```

### <a name="remarks"></a>설명

글꼴, 문자 집합을 지정할 수 있으며 피치 및 패밀리의 리본 글꼴 콤보에 포함할 글꼴 상자에 [생성자](#cmfcribbonfontcombobox) 를 호출 하거나이 클래스에 대 한 [CMFCRibbonFontComboBox::BuildFonts](#buildfonts).

##  <a name="setfont"></a>  CMFCRibbonFontComboBox::SetFont

콤보 상자에서 지정된 글꼴을 선택합니다.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>매개 변수

' lpszName * 선택 글꼴의 이름을 지정 합니다.

*nCharSet*<br/>
선택한 글꼴의 문자 집합을 지정 합니다.

*bExact*<br/>
문자 집합을 글꼴;를 선택 하는 경우와 일치 해야 함을 지정. 글꼴을 선택 하는 경우 문자 집합을 지정 하려면 FALSE는 무시할 수 있습니다.

### <a name="return-value"></a>반환 값

지정된 된 글꼴을 찾아 선택 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

##  <a name="getcharset"></a>  CMFCRibbonFontComboBox::GetCharSet

지정된 문자 집합을 반환합니다.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>반환 값

문자 집합 (Windows SDK 설명서의 LOGFONT 참조).

### <a name="remarks"></a>설명

##  <a name="getfonttype"></a>  CMFCRibbonFontComboBox::GetFontType

콤보 상자에 표시할 글꼴 종류를 반환합니다. 유효한 옵션 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE 또는 이러한 옵션의 비트 조합입니다.

```
int GetFontType() const;
```

### <a name="return-value"></a>반환 값

글꼴 종류를 (EnumFontFamProc Windows SDK 설명서의 참조).

### <a name="remarks"></a>설명

##  <a name="getpitchandfamily"></a>  CMFCRibbonFontComboBox::GetPitchAndFamily

콤보 상자에 표시되는 글꼴의 피치 및 패밀리를 반환합니다.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>반환 값

피치 및 패밀리 (Windows SDK 설명서의 LOGFONT 참조).

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonComboBox 클래스](../../mfc/reference/cmfcribboncombobox-class.md)
