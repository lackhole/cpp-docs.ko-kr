---
title: CFont 클래스
ms.date: 11/04/2016
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
ms.openlocfilehash: 04136b3550675f0e50f905047fee551e27da7069
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768110"
---
# <a name="cfont-class"></a>CFont 클래스

Windows GDI(그래픽 디바이스 인터페이스) 글꼴을 캡슐화하고 글꼴 조작을 위한 멤버 함수를 제공합니다.

## <a name="syntax"></a>구문

```
class CFont : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFont::CFont](#cfont)|`CFont` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFont::CreateFont](#createfont)|초기화는 `CFont` 지정된 된 특성을 사용 하 여 합니다.|
|[CFont::CreateFontIndirect](#createfontindirect)|초기화를 `CFont` 에 지정 된 특성을 가진 개체는 `LOGFONT` 구조입니다.|
|[CFont::CreatePointFont](#createpointfont)|초기화는 `CFont` 지정 된 높이 사용 하 여 지점 및 서체의 1/10 초 단위로 측정 합니다.|
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|동일 `CreateFontIndirect` 제외 하 고 글꼴 높이 10 배로 논리 단위 보다는 지점에서 측정 됩니다.|
|[CFont::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CFont` Windows HFONT 지정 되 면 개체입니다.|
|[CFont::GetLogFont](#getlogfont)|채웁니다를 `LOGFONT` 에 연결 된 논리 글꼴에 대 한 정보는 `CFont` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[HFONT CFont::operator](#operator_hfont)|Windows GDI 글꼴 핸들에 연결 하는 반환 된 `CFont` 개체입니다.|

## <a name="remarks"></a>설명

사용 하는 `CFont` 개체를 생성을 `CFont` 개체를 사용 하 여 Windows 글꼴 연결 [CreateFont](#createfont)를 [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), 또는 [CreatePointFontIndirect](#createpointfontindirect), 개체의 멤버 함수를 사용 하 여 글꼴을 조작 합니다.

`CreatePointFont` 하 고 `CreatePointFontIndirect` 함수는 보다 사용 하기가 `CreateFont` 또는 `CreateFontIndirect` 하므로 이러한 변환을 수행 높이 대 한 글꼴의 포인트 크기에서 논리 단위를 자동으로.

에 대 한 자세한 `CFont`를 참조 하세요 [그래픽 개체](../../mfc/graphic-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cfont"></a>  CFont::CFont

`CFont` 개체를 생성합니다.

```
CFont();
```

### <a name="remarks"></a>설명

결과 개체를 사용 하 여 초기화 `CreateFont`, `CreateFontIndirect`를 `CreatePointFont`, 또는 `CreatePointFontIndirect` 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

##  <a name="createfont"></a>  CFont::CreateFont

초기화는 `CFont` 지정된 특징을 갖는 개체입니다.

```
BOOL CreateFont(
    int nHeight,
    int nWidth,
    int nEscapement,
    int nOrientation,
    int nWeight,
    BYTE bItalic,
    BYTE bUnderline,
    BYTE cStrikeOut,
    BYTE nCharSet,
    BYTE nOutPrecision,
    BYTE nClipPrecision,
    BYTE nQuality,
    BYTE nPitchAndFamily,
    LPCTSTR lpszFacename);
```

### <a name="parameters"></a>매개 변수

*nHeight*<br/>
원하는 높이 (논리 단위)의 글꼴을 지정합니다. 참조를 `lfHeight` 의 멤버는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)구조에 대 한 Windows sdk입니다. 절대값 *nHeight* 변환 된 후 16,384 장치 단위를 초과 하지 않아야 합니다. 모든 높이 비교의 경우 요청 된 크기를 초과 하는 모든 글꼴 요청 된 크기를 초과 하지 않는 가장 큰 글꼴 또는 가장 작은 글꼴 크기에 대 한 글꼴 매퍼가 찾습니다.

*nWidth*<br/>
글꼴에서 문자의 평균 너비 (논리 단위)에 지정합니다. 하는 경우 *nWidth* 가 0 이면 장치의 가로 세로 비율 차이의 절대값에 의해 결정 되는 가장 가까운 일치 항목을 찾을 사용 가능한 글꼴 디지털화 가로 세로 비율과 일치 합니다.

*nEscapement*<br/>
글자 방향 벡터와 화면의 x 축 사이의 각도 (0.1도 단위로)을 지정합니다. 글자 방향 벡터는 줄의 첫 번째 및 마지막 문자의 원본을 통해 줄입니다. 각도 x 축에서 시계 반대 방향으로 측정 됩니다. 참조를 `lfEscapement` 의 멤버는 `LOGFONT` 구조에 대 한 자세한 내용은 Windows SDK의 합니다.

*nOrientation*<br/>
(0.1도 단위로) 문자의 기준선과 x 축 사이의 각도 지정합니다. 각도 y 방향이 고 y 방향을 중인지는 좌표계에 대 한 x-축에서 시계 방향으로 좌표계에 대 한 x 축에서 시계 반대 방향으로 측정 됩니다.

*nWeight*<br/>
잉크가 픽셀 당 1000 단위로 글꼴 두께 지정합니다. 참조를 *은* 멤버는 `LOGFONT` 자세한 내용은 Windows SDK의 구조입니다. 설명된 값은 근사값입니다. 실제 모양 서체에 따라 달라 집니다. 일부 글꼴 FW_NORMAL, FW_REGULAR, 및 FW_BOLD 가중치만 있어야 합니다. FW_DONTCARE 지정 된 경우에 기본 가중치 사용 됩니다.

*bItalic*<br/>
글꼴이 기울임꼴인지 여부를 지정 합니다.

*bUnderline*<br/>
글꼴에 밑줄이 있는지 여부를 지정 합니다.

*cStrikeOut*<br/>
글꼴의 문자는 취소선 여부를 지정 합니다. 경우 취소선 글꼴을 지정 합니다. 0이 아닌 값으로 설정 합니다.

*nCharSet*<br/>
글꼴의 문자 setSee 지정는 `lfCharSet` 의 멤버는 `LOGFONT` 값의 목록을 Windows SDK의 구조입니다.

OEM 문자 집합은 시스템에 따라 다릅니다.

다른 문자 집합을 사용 하 여 글꼴은 시스템에 있을 수 있습니다. 알 수 없는 문자 집합을 사용 하 여 글꼴을 사용 하는 응용 프로그램 변환 또는 해당 글꼴을 사용 하 여 렌더링할 수 있는 문자열을 해석 시도 하지 않아야 합니다. 대신 문자열을 출력 장치 드라이버에 직접 전달 되어야 합니다.

글꼴 매퍼 DEFAULT_CHARSET 값을 사용 하지 않습니다. 응용 프로그램 이름 및 논리 글꼴을 완벽 하 게 설명 하는 글꼴의 크기를 허용 하려면이 값을 사용할 수 있습니다. 지정한 이름 가진 글꼴을 존재 하지 않는 경우 지정된 된 글꼴에 대 한 모든 문자 집합에서 글꼴을 대체할 수 있습니다. 예기치 않은 결과 방지 하려면 응용 프로그램에서 DEFAULT_CHARSET 값을 제한적으로 사용 해야 합니다.

*nOutPrecision*<br/>
원하는 출력 정밀도를 지정합니다. 출력 정밀도 정의 요청된 된 글꼴의 높이, 너비, 문자, 이스케이프를 방향과 피치 출력 얼마나 밀접 하 게 일치 해야 합니다. 참조를 `lfOutPrecision` 의 멤버는 `LOGFONT` 값 목록과 자세한 정보에 대 한 Windows SDK에는 구조입니다.

*nClipPrecision*<br/>
원하는 클리핑 정밀도 지정합니다. 클리핑 정밀도 부분적으로 클리핑 영역 외부에 있는 문자 클리핑 하는 방법을 정의 합니다. 참조를 `lfClipPrecision` 의 멤버는 `LOGFONT` 값의 목록을 Windows SDK의 구조입니다.

포함된 된 읽기 전용 글꼴을 사용 하려면 응용 프로그램 CLIP_ENCAPSULATE 지정 해야 합니다.

장치, TrueType 및 벡터 글꼴의 일관 된 회전을 달성 하려면 응용 프로그램 사용 OR 연산자를 결합할 수 있습니다 CLIP_LH_ANGLES 값을 사용 하 여 다른 *nClipPrecision* 값입니다. 모든 글꼴에 대해 회전 좌표계의 방향을 왼쪽 인지에 따라 달라 집니다는 CLIP_LH_ANGLES 비트가 설정 된 경우 또는 오른손 합니다. (좌표 시스템의 방향에 대 한 자세한 내용은 참조에 대 한 설명을 합니다 *nOrientation* 매개 변수.) CLIP_LH_ANGLES 설정 되어 있지 않으면 장치 글꼴 항상, 시계 반대 방향으로 회전 하지만 다른 글꼴의 회전 좌표계의 방향에 따라 달라 집니다.

*nQuality*<br/>
GDI 해야는 실제 실제 글꼴의 논리 글꼴 특성을 일치 시 키 려 신중 하 게 정의 하는 글꼴의 출력 품질을 지정 합니다. 참조를 `lfQuality` 의 멤버는 `LOGFONT` 값의 목록을 Windows SDK의 구조입니다.

*nPitchAndFamily*<br/>
폭 및 글꼴 패밀리를 지정합니다. 참조를 `lfPitchAndFamily` 의 멤버는 `LOGFONT` 값 목록과 자세한 정보에 대 한 Windows SDK에는 구조입니다.

*lpszFacename*<br/>
`CString` 또는 글꼴의 서체 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 문자열의 길이 30 자를 초과할 수 없습니다. Windows [EnumFontFamilies](/windows/desktop/api/wingdi/nf-wingdi-enumfontfamiliesa) 현재 사용 가능한 모든 글꼴을 열거 하는 함수를 사용할 수 있습니다. 하는 경우 *lpszFacename* 가 null 인 경우 GDI 장치 독립적인 서체를 사용 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 장치 컨텍스트에 대 한 글꼴으로 글꼴을 선택할 수 있습니다.

`CreateFont` 함수에서 새 Windows GDI 글꼴을 만들지 않습니다. 사용 가능한 실제 글꼴에서 가장 가까운 GDI를 선택 하기만 합니다.

응용 프로그램 논리 글꼴을 만들 때 대부분의 매개 변수에 대 한 기본 설정을 사용할 수 있습니다. 항상 특정 값 제공 되어야 하는 매개 변수가 *nHeight* 하 고 *lpszFacename*합니다. 하는 경우 *nHeight* 하 고 *lpszFacename* 설정 되지 않은 응용 프로그램에서 만든 논리 글꼴은 장치에 따라 다릅니다.

사용을 완료 하면 합니다 `CFont` 하 여 만든 개체를 `CreateFont` 함수를 사용 하 여 `CDC::SelectObject` 다른 글꼴로 그려지거나 장치 컨텍스트로 선택 하려면 삭제는 `CFont` 더 이상 필요 없는 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect

초기화를 `CFont` 에 지정 된 특성을 가진 개체를 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)구조입니다.

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>매개 변수

*lpLogFont*<br/>
가리키는 `LOGFONT` 논리 글꼴의 특징을 정의 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 모든 장치에 대 한 현재 글꼴과 글꼴을 선택할 수 있습니다.

이 글꼴에 지정 된 특성에는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 구조입니다. 사용 하 여는 글꼴을 선택 하는 경우는 [cdc:: selectobject](../../mfc/reference/cdc-class.md#selectobject) 멤버 함수는 GDI 글꼴 매퍼 일치 시 키 려는 기존 실제 글꼴을 사용 하 여 논리 글꼴입니다. 글꼴 매퍼를 하지 못한 경우 논리 글꼴에 대 한 정확한 일치 특성을 가진 여러 가지 가능한 요청 된 특성으로 일치 하는 대체 글꼴을 제공 합니다.

더 이상 필요 합니다 `CFont` 하 여 만든 개체를 `CreateFontIndirect` 함수를 사용 하 여 `CDC::SelectObject` 다른 글꼴로 그려지거나 장치 컨텍스트로 선택 하려면 삭제는 `CFont` 더 이상 필요 없는 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

##  <a name="createpointfont"></a>  CFont::CreatePointFont

이 함수 및 크기를 지정 된 서체의 글꼴 만들기 하는 간단한 방법을 제공 합니다.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>매개 변수

*nPointSize*<br/>
10 배로 요소의 글꼴 높이 요청 합니다. (12 포인트 글꼴을 요청 하는 120 전달할 예를 들어.)

*lpszFaceName*<br/>
`CString` 또는 글꼴의 서체 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 문자열의 길이 30 자를 초과할 수 없습니다. Windows ' EnumFontFamilies 함수는 현재 사용 가능한 모든 글꼴 열거를 사용할 수 있습니다. 하는 경우 *lpszFaceName* 가 null 인 경우 GDI 장치 독립적인 서체를 사용 합니다.

*pDC*<br/>
에 대 한 포인터를 [CDC](../../mfc/reference/cdc-class.md) 개체의 높이 변환 하는 데 *nPointSize* 논리 단위입니다. NULL 인 경우 화면 장치 컨텍스트 변환 하는 데 사용 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

높이 자동으로 변환 *nPointSize* 논리 단위에 CDC 개체를 사용 하 여 가리키는 *pDC*합니다.

사용을 완료 하면 합니다 `CFont` 하 여 만든 개체를 `CreatePointFont` 함수를 먼저 장치 컨텍스트에서 글꼴을 선택한 다음 삭제를 `CFont` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect

이 함수는 동일 [CreateFontIndirect](#createfontindirect) 점을 제외 하 고는 `lfHeight` 의 멤버는 `LOGFONT` 장치 대신 지점 단위의 1/10으로 해석 됩니다.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>매개 변수

*lpLogFont*<br/>
가리키는 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 논리 글꼴의 특징을 정의 하는 구조입니다. 합니다 `lfHeight` 의 멤버는 `LOGFONT` 구조 논리 단위 보다는 지점의 1/10 초 단위로 측정 됩니다. (예를 들어 설정 `lfHeight` 120 12 포인트 글꼴을 요청 합니다.)

*pDC*<br/>
에 대 한 포인터를 [CDC](../../mfc/reference/cdc-class.md) 개체의 높이 변환 하는 데 사용할 `lfHeight` 논리 단위입니다. NULL 인 경우 화면 장치 컨텍스트 변환 하는 데 사용 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수에서 높이 자동으로 변환 `lfHeight` 논리 단위에 CDC 개체를 사용 하 여 가리키는 *pDC* 전달 하기 전에 `LOGFONT` 구조 Windows에 로그온 합니다.

사용을 완료 하면 합니다 `CFont` 하 여 만든 개체를 `CreatePointFontIndirect` 함수를 먼저 장치 컨텍스트에서 글꼴을 선택한 다음 삭제를 `CFont` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

##  <a name="fromhandle"></a>  CFont::FromHandle

에 대 한 포인터를 반환 합니다.는 `CFont` HFONT 핸들을 Windows GDI 글꼴 개체에 지정 된 경우 개체입니다.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>매개 변수

*hFont*<br/>
Windows 글꼴을 HFONT 핸들입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CFont` 성공 하면 NULL 개체입니다.

### <a name="remarks"></a>설명

경우는 `CFont` 개체가 이미 임시 핸들에 연결 되지 않은 `CFont` 개체를 만들어 연결 합니다. 이 임시 `CFont` 개체는 다음에 응용 프로그램에 유휴 시간 이벤트 루프에서 될 때까지 모든 임시 그래픽 시간이 개체는 삭제만 유효 합니다. 또 다른 방법은 한 창 메시지를 처리 하는 동안에 임시 개체가 올바른지 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

##  <a name="getlogfont"></a>  CFont::GetLogFont

복사본을 검색 하려면이 함수를 호출 합니다 `LOGFONT` 의 구조 `CFont`합니다.

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>매개 변수

*pLogFont*<br/>
에 대 한 포인터를 [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) 글꼴 정보를 받는 구조체입니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 고 그렇지 하는 경우에 0이 아닙니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

##  <a name="operator_hfont"></a>  HFONT CFont::operator

이 연산자를 사용 하 여 연결할 글꼴의 Windows GDI 핸들을 가져올 수는 `CFont` 개체입니다.

```
operator HFONT() const;
```

### <a name="return-value"></a>반환 값

Windows GDI 글꼴 개체의 핸들에 연결 된 `CFont` 성공 하면 NULL입니다.

### <a name="remarks"></a>설명

이 연산자에서 변환에 대 한 자동으로 사용 되므로 `CFont` 에 [글꼴 및 텍스트](/windows/desktop/gdi/fonts-and-text)를 전달할 수 있습니다 `CFont` HFONTs 예상 하는 함수 개체입니다.

그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [그래픽 개체](/windows/desktop/gdi/graphic-objects) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>참고자료

[MFC Sample HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
