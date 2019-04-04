---
title: CMFCPropertyGridFontProperty 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
ms.openlocfilehash: b348dc2ac68ced89fb0702073f57a114befaf1cb
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769357"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty 클래스

`CMFCPropertyGridFileProperty` 클래스 글꼴 선택 대화 상자를 여는 속성 목록 컨트롤 항목을 지원 합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|`CMFCPropertyGridFontProperty` 개체를 생성합니다.|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|속성 값의 텍스트 표현에 서식을 지정합니다. (재정의 [cmfcpropertygridproperty:: Formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|글꼴 대화 상자에서 사용자가 선택한 글꼴 색을 검색 합니다.|
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|글꼴 대화 상자에서 사용자가 선택한 글꼴을 검색 합니다.|
|`CMFCPropertyGridFontProperty::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|`CMFCPropertyGridFontProperty::OnClickButton`|사용자가 속성에 포함된 단추를 클릭하면 프레임워크에서 호출됩니다. (재정의 [cmfcpropertygridproperty:: Onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertygridctrl.h

##  <a name="cmfcpropertygridfontproperty"></a>  CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty

`CMFCPropertyGridFontProperty` 개체를 생성합니다.

```
CMFCPropertyGridFontProperty(
    const CString& strName,
    LOGFONT& lf,
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0,
    COLORREF color = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
[in] 속성의 이름입니다.

*lf*<br/>
[in] 글꼴의 특성을 지정 하는 논리 글꼴 구조입니다.

*dwFontDialogFlags*<br/>
[in] 속성 값 드롭다운 단추를 클릭할 때 표시 되는 글꼴 대화 상자에 적용 되는 스타일입니다. 기본값은 CF_EFFECTS 및 CF_SCREENFONTS의 비트 조합 (OR)입니다. 자세한 내용은 참조는 *플래그* 의 매개 변수를 [CHOOSEFONT 구조](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta)합니다.

*lpszDescr*<br/>
[in] Font 속성의 설명입니다. 기본값은 NULL입니다.

*dwData*<br/>
[in] 응용 프로그램별 데이터, 정수 등의 속성을 사용 하 여 연결 된 다른 데이터에 대 한 포인터입니다. 기본값은 0입니다.

*color*<br/>
[in] 글꼴의 색입니다. 기본값은 기본 색입니다.

### <a name="remarks"></a>설명

`CMFCPropertyGridFontProperty` 개체 속성 표 글꼴 컨트롤의 글꼴 속성을 나타냅니다.

### <a name="example"></a>예제

다음 예제에서는 개체를 생성 하는 방법은 `CMFCPropertyGridFontProperty` 클래스입니다. 이 예제는의 일부를 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

##  <a name="getcolor"></a>  CMFCPropertyGridFontProperty::GetColor

글꼴 대화 상자에서 사용자가 선택한 글꼴 색을 검색 합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>반환 값

선택한 글꼴 색을 나타내는 RGB 색 값입니다.

### <a name="remarks"></a>설명

##  <a name="getlogfont"></a>  CMFCPropertyGridFontProperty::GetLogFont

글꼴 대화 상자에서 사용자가 선택한 글꼴을 검색 합니다.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 선택한 글꼴을 설명 하는 구조입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty 클래스](../../mfc/reference/cmfcpropertygridproperty-class.md)
