---
title: CMFCFontComboBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
ms.openlocfilehash: ccc4e545b2274d6dbb9989cfb9c047de819b8d32
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237474"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox 클래스

`CMFCFontComboBox` 클래스 글꼴 목록이 포함 된 콤보 상자 컨트롤을 만듭니다.

## <a name="syntax"></a>구문

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|`CMFCFontComboBox` 개체를 생성합니다.|
|`CMFCFontComboBox::~CMFCFontComboBox`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|현재 글꼴 콤보 상자 컨트롤의 정렬 된 목록 상자에서 새 항목의 상대 위치를 확인 하기 위해 프레임 워크에서 호출 됩니다. (재정의 [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|현재 글꼴 콤보 상자 컨트롤에서 지정된 된 항목을 그리기 위해 프레임 워크에서 호출 됩니다. (재정의 [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|현재 선택한 글꼴에 대 한 정보를 검색합니다.|
|`CMFCFontComboBox::MeasureItem`|현재 글꼴 콤보 상자 컨트롤에서 목록 상자 크기의 Windows를 알리기 위해 프레임 워크에서 호출 됩니다. (재정의 [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|디스패치 되기 전에 창 메시지를 변환 합니다 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 함수입니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMFCFontComboBox::SelectFont](#selectfont)|글꼴 콤보 상자에서 지정된 된 조건과 일치 하는 글꼴을 선택 합니다.|
|[CMFCFontComboBox::Setup](#setup)|글꼴 콤보 상자에서 항목 목록을 초기화합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|현재 글꼴 콤보 상자의 항목 레이블을 그리는 데 사용할 글꼴을 프레임 워크를 나타냅니다.|

## <a name="remarks"></a>설명

사용 하는 `CMFCFontComboBox` 대화 상자에서 개체를 추가 `CMFCFontComboBox` 변수 대화 상자 클래스를 합니다. 그런 다음 합니다 `OnInitDialog` 호출 대화 상자 클래스의 메서드를 [CMFCFontComboBox::Setup](#setup) 콤보 상자 컨트롤에서 항목 목록을 초기화 하는 방법입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxfontcombobox.h

##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox

`CMFCFontComboBox` 개체를 생성합니다.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont

현재 선택한 글꼴에 대 한 정보를 검색합니다.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터 [CMFCFontInfo 클래스](../../mfc/reference/cmfcfontinfo-class.md) 글꼴을 설명 하는 개체입니다. 콤보 상자의 없는 글꼴을 선택 하는 경우 NULL 수 있습니다.

### <a name="remarks"></a>설명

##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont

현재 글꼴 콤보 상자의 항목 레이블을 그리는 데 사용할 글꼴을 프레임 워크를 나타냅니다.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>설명

이 멤버를 각 항목 레이블 그릴 같은 글꼴을 사용 하기 위해 프레임 워크를 TRUE로 설정 합니다. 이 멤버 이름이 레이블로 동일 글꼴을 사용 하 여 각 항목 레이블을 그리기 위해 프레임 워크를 FALSE로 설정 합니다. 이 멤버의 기본값은 FALSE입니다.

##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont

글꼴 콤보 상자에서 지정된 된 조건과 일치 하는 글꼴을 선택 합니다.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>매개 변수

*pDesc*<br/>
[in] 글꼴 설명 개체를 가리킵니다.

*lpszName*<br/>
[in] 글꼴 이름을 지정합니다.

*nCharSet*<br/>
[in] 문자 집합을 지정합니다. 기본값은 DEFAULT_CHARSET 합니다. 자세한 내용은 참조 하세요. 합니다 `lfCharSet` 의 멤버는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 구조입니다.

### <a name="return-value"></a>반환 값

글꼴 콤보 상자의 항목 설명 개체를 지정 된 글꼴 또는 글꼴 이름과 charset; 일치 하는 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 선택 하 고 지정한 글꼴에 해당 하는 글꼴 콤보 상자에 있는 항목으로 스크롤합니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `SelectFont` 의 메서드는 `CMFCFontComboBox` 클래스입니다. 이 예제는의 일부를 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>  CMFCFontComboBox::Setup

글꼴 콤보 상자에서 항목 목록을 초기화합니다.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>매개 변수

*nFontType*<br/>
[in] 글꼴 종류를 지정합니다. 기본값은 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE의 비트 조합 (OR)입니다.

*nCharSet*<br/>
[in] 글꼴 문자 집합을 지정 합니다. 기본값은 DEFAULT_CHARSET 합니다.

*nPitchAndFamily*<br/>
[in] 글꼴 피치 및 패밀리를 지정합니다. 기본값은 DEFAULT_PITCH 합니다.

### <a name="return-value"></a>반환 값

글꼴 콤보 상자 성공적으로 초기화 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 된 매개 변수와 일치 하는 현재 설치 된 글꼴 열거 하 고 글꼴 콤보 상자에서 해당 글꼴 이름을 삽입 하 여 글꼴 콤보 상자를 초기화 합니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `Setup` 의 메서드는 `CMFCFontComboBox` 클래스입니다. 이 예제는의 일부를 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo 클래스](../../mfc/reference/cmfcfontinfo-class.md)
