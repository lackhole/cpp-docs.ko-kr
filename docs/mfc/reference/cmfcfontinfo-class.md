---
title: CMFCFontInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
ms.openlocfilehash: 930aceb4514195f0e844c35d326b52d9cd8d31fa
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781330"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo 클래스

`CMFCFontInfo` 클래스 이름 및 글꼴의 기타 특성에 설명 합니다.

## <a name="syntax"></a>구문

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMFCFontInfo`|`CMFCFontInfo` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCFontInfo::GetFullName](#getfullname)|연결 된 글꼴 이름과 해당 문자 집합 (스크립트)를 검색 합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|연결 된 문자 집합 (스크립트)을 지정 하는 값입니다.|
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|피치 및 글꼴의 제품군을 지정 하는 값입니다.|
|[CMFCFontInfo::m_nType](#m_ntype)|글꼴의 유형을 지정 하는 값입니다.|
|[CMFCFontInfo::m_strName](#m_strname)|글꼴;의 이름 예를 들어 **Arial**합니다.|
|[CMFCFontInfo::m_strScript](#m_strscript)|연결 된 문자 집합 (스크립트)의 이름입니다.|

## <a name="remarks"></a>설명

연결할 수 있습니다는 `CMFCFontInfo` 개체의 항목에는 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 클래스입니다. 호출 된 [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) 에 대 한 포인터를 검색 하는 메서드를 `CMFCFontInfo` 개체입니다.

## <a name="example"></a>예제

다음 예제에서는의 다양 한 멤버를 사용 하는 방법에 설명 합니다 `CMFCFontInfo` 클래스입니다. 예제에 가져오는 방법을 보여 줍니다는 `CMFCFontInfo` 에서 개체를 `CMFCRibbonFontComboBox`, 및 지역 변수를 액세스 하는 방법. 이 예제는의 일부를 [MSOffice 2007 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarfontcombobox.h

##  <a name="cmfcfontinfo"></a>  CMFCFontInfo::CMFCFontInfo

`CMFCFontInfo` 개체를 생성합니다.

```
CMFCFontInfo(
    LPCTSTR lpszName,
    LPCTSTR lpszScript,
    BYTE nCharSet,
    BYTE nPitchAndFamily,
    int nType);

CMFCFontInfo(const CMFCFontInfo& src);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
[in] 글꼴의 이름입니다. 자세한 내용은 참조 하세요. 합니다 `lfFaceName` 의 멤버는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 구조입니다.

*lpszScript*<br/>
[in] 글꼴의 스크립트 (문자 집합)의 이름입니다.

*nCharSet*<br/>
[in] 글꼴의 문자 집합 (스크립트)을 지정 하는 값입니다. 자세한 내용은 참조 하세요. 합니다 `lfCharSet` 의 멤버는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 구조입니다.

*nPitchAndFamily*<br/>
[in] 피치 및 글꼴의 제품군을 지정 하는 값입니다. 자세한 내용은 참조 하세요. 합니다 `lfPitchAndFamily` 의 멤버는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 구조입니다.

*nType*<br/>
[in] 글꼴 종류를 지정 하는 값입니다. 이 매개 변수는 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE의 비트 조합 (OR) 수 있습니다.

*src*<br/>
[in] 기존 `CMFCFontInfo` 멤버가이 생성 되는 개체 `CMFCFontInfo` 개체입니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

이 설명서에서는 용어 *문자 집합* 하 고 *스크립트* 서로 교환해 서입니다. A *스크립트*, 문자 및 하나 이상의 언어에서 해당 문자를 작성 하는 것에 대 한 규칙의 컬렉션인는으로 쓰는 쓰기 시스템 라고도 합니다. 에 알파벳 및 스크립트에 사용 되는 문장 부호 문자의 컬렉션에 포함 됩니다. 예를 들어 미국에서 사용 되는 것와 해당 알파벳 A부터 Z 까지의 문자가 포함 됩니다. 라틴어 스크립트 영어에 사용 됩니다. 합니다 `lfCharSet` 의 멤버는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 구조에는 문자 집합을 지정 합니다. 예를 들어 값 굴림 라틴 알파벳을 포함 하는 ANSI 문자 집합을 지정 합니다.

##  <a name="getfullname"></a>  CMFCFontInfo::GetFullName

연결 된 글꼴 이름과 해당 문자 집합 (스크립트)를 검색 합니다.

```
CString GetFullName() const;
```

### <a name="return-value"></a>반환 값

글꼴 이름 및 스크립트를 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 글꼴의 전체 이름을 가져옵니다. 예를 들어 글꼴 이름을 **Arial** 글꼴 스크립트 이며 **키릴 자모**,이 메서드는 "Arial (키릴 자모)"를 반환 합니다.

##  <a name="m_ncharset"></a>  CMFCFontInfo::m_nCharSet

연결 된 문자 집합 (스크립트)을 지정 하는 값입니다.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>설명

자세한 내용은 참조는 *nCharSet* 의 매개 변수를 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.

##  <a name="m_npitchandfamily"></a>  CMFCFontInfo::m_nPitchAndFamily

피치 (지점 크기) 및 글꼴의 제품군 (예: serif, sans serif 및 고정 폭)을 지정 하는 값입니다.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>설명

자세한 내용은 참조는 *nPitchAndFamily* 의 매개 변수를 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.

##  <a name="m_ntype"></a>  CMFCFontInfo::m_nType

글꼴의 유형을 지정 하는 값입니다.

```
const int m_nType;
```

### <a name="remarks"></a>설명

자세한 내용은 참조는 *n 형식* 의 매개 변수를 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.

##  <a name="m_strname"></a>  CMFCFontInfo::m_strName

글꼴의 이름: 예를 들어 **Arial**합니다.

```
const CString m_strName;
```

### <a name="remarks"></a>설명

자세한 내용은 참조는 *lpszName* 의 매개 변수를 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.

##  <a name="m_strscript"></a>  CMFCFontInfo::m_strScript

연결 된 문자 집합 (스크립트)의 이름입니다.

```
const CString m_strScript;
```

### <a name="remarks"></a>설명

자세한 내용은 참조는 *lpszScript* 의 매개 변수를 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox 클래스](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
