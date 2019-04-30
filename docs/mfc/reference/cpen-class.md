---
title: CPen 클래스
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: 8510c29571e6a370c7948ebe49e53b2c22dbfb9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372922"
---
# <a name="cpen-class"></a>CPen 클래스

Windows GDI(그래픽 디바이스 인터페이스) 펜을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPen : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPen::CPen](#cpen)|`CPen` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPen::CreatePen](#createpen)|지정 된 스타일, 너비 및 브러시 특성을 사용 하 여 논리적 외관 또는 기하학적 펜을을 만들고에 연결 된 `CPen` 개체입니다.|
|[CPen::CreatePenIndirect](#createpenindirect)|펜 스타일, 두께 및 색에 지정 된을 만드는 데는 [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) 구조체와 연결 하는 `CPen` 개체입니다.|
|[CPen::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CPen` Windows HPEN 지정 되 면 개체입니다.|
|[CPen::GetExtLogPen](#getextlogpen)|가져옵니다는 [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) 기본 구조입니다.|
|[CPen::GetLogPen](#getlogpen)|가져옵니다를 [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) 기본 구조입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CPen::operator HPEN](#operator_hpen)|에 연결 된 Windows 핸들을 반환 합니다 `CPen` 개체입니다.|

## <a name="remarks"></a>설명

사용 하 여 대 한 자세한 내용은 `CPen`를 참조 하세요 [그래픽 개체](../../mfc/graphic-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cpen"></a>  CPen::CPen

`CPen` 개체를 생성합니다.

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*nPenStyle*<br/>
펜 스타일을 지정합니다. 생성자의 첫 번째 버전에서이 매개 변수는 다음 값 중 하나일 수 있습니다.

- PS_SOLID solid 펜을 만듭니다.

- PS_DASH 파선된 펜을 만듭니다. 펜 너비가 1 이하인, 장치 단위 하는 경우에 유효 합니다.

- PS_DOT은 점으로 구분 된 펜을 만듭니다. 펜 너비가 1 이하인, 장치 단위 하는 경우에 유효 합니다.

- PS_DASHDOT 교대로 반복 되는 펜을 대시 및 점을 만듭니다. 펜 너비가 1 이하인, 장치 단위 하는 경우에 유효 합니다.

- PS_DASHDOTDOT 대시 및 이중 점 교대로 반복 되는 펜을 만듭니다. 펜 너비가 1 이하인, 장치 단위 하는 경우에 유효 합니다.

- PS_NULL null 펜을 만듭니다.

- 경계 사각형을 지정 하는 함수 출력 PS_INSIDEFRAME 닫힌된 도형의 프레임 내에서 선을 그리는 펜을 생성 하 여 만듭니다 Windows GDI (예를 들어 합니다 `Ellipse`, `Rectangle`를 `RoundRect`, `Pie`, 및 `Chord`멤버 함수). 경계 사각형을 지정 하지 않는 Windows GDI 출력 함수를 사용 하 여이 스타일은 사용 하는 경우 (예를 들어를 `LineTo` 멤버 함수), 펜의 그리기 영역 프레임으로 제한 되지 않습니다.

두 번째 버전은 `CPen` 생성자의 형식, 스타일, 끝 단면 및 조인 특성 조합을 지정 합니다. 비트 OR 연산자를 사용 하 여 각 범주에서 값을 결합 되어야 합니다 (&#124;). 펜 형식에는 다음 값 중 하나일 수 있습니다.

- PS_GEOMETRIC 기하학적 펜을 만듭니다.

- PS_COSMETIC 성형 펜을을 만듭니다.

   두 번째 버전은 `CPen` 의 다음 펜 스타일을 추가 하는 생성자 *nPenStyle*:

- PS_ALTERNATE 다른 모든 픽셀을 설정 하는 펜을 만듭니다. (이 스타일은 표면적인 펜에만 적용할 수 있습니다.)

- 펜 스타일 배열을 사용 하는 사용자가 제공한 PS_USERSTYLE 만듭니다.

   끝 캡은 다음 값 중 하나일 수 있습니다.

- PS_ENDCAP_ROUND 끝 캡 반올림 됩니다.

- PS_ENDCAP_SQUARE 끝 캡 사각형이 됩니다.

- PS_ENDCAP_FLAT 끝 캡은 평면입니다.

   조인에는 다음 값 중 하나일 수 있습니다.

- PS_JOIN_BEVEL 조인 경사진 됩니다.

- PS_JOIN_MITER 조인 된 각으로 설정 된 현재 제한 내에서 서로 [SetMiterLimit](/windows/desktop/api/wingdi/nf-wingdi-setmiterlimit) 함수입니다. 이 제한을 초과 하는 조인, 경사진 합니다.

- PS_JOIN_ROUND 조인 반올림 됩니다.

*nWidth*<br/>
펜의 너비를 지정합니다.

- 생성자의 첫 번째 버전에서는이 값이 0 인 경우 장치 단위에서 너비는 항상 매핑 모드에 관계 없이 1 픽셀입니다.

- 생성자의 두 번째 버전에 대 한 경우 *nPenStyle* PS_GEOMETRIC는 너비를 논리 단위로 지정 됩니다. 하는 경우 *nPenStyle* PS_COSMETIC은 너비가 1로 설정 해야 합니다.

*crColor*<br/>
펜에 대 한 RGB 색을 포함합니다.

*pLogBrush*<br/>
가리키는 `LOGBRUSH` 구조입니다. 경우 *nPenStyle* PS_COSMETIC는 *lbColor* 의 멤버는 `LOGBRUSH` 펜의 색을 지정 하는 구조 및 *lbStyle* 의 멤버는 `LOGBRUSH` 구조는 BS_SOLID로 설정 되어야 합니다. 하는 경우 *nPenStyle* PS_GEOMETRIC에는 모든 멤버에서 펜의 브러시 특성을 지정 하는 데 사용 해야 합니다.

*nStyleCount*<br/>
워드 단위에서 길이 지정 합니다 *lpStyle* 배열입니다. 이 값은 경우에는 0 이어야 *nPenStyle* PS_USERSTYLE 아닙니다.

*lpStyle*<br/>
워드 값의 배열 가리킵니다. 사용자 정의 스타일의 첫 번째 대시의 길이 지정 하는 첫 번째 값, 두 번째 값의 첫 번째 공간 및 등의 길이 지정 합니다. 이 포인터 경우 NULL 이어야 합니다 *nPenStyle* PS_USERSTYLE 아닙니다.

### <a name="remarks"></a>설명

인수가 없는 생성자를 사용 하는 경우 결과 초기화 해야 합니다 `CPen` 개체를 `CreatePen`를 `CreatePenIndirect`, 또는 `CreateStockObject` 멤버 함수입니다.

인수를 받는 생성자를 사용 하면 추가 초기화가 필요 합니다. 오류가 발생 하는 경우 생성자는 인수 없이 항상 성공 하는 동안 인수를 사용 하 여 생성자에서 예외를 throw 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

##  <a name="createpen"></a>  CPen::CreatePen

지정 된 스타일, 너비 및 브러시 특성을 사용 하 여 논리적 외관 또는 기하학적 펜을을 만들고에 연결 된 `CPen` 개체입니다.

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*nPenStyle*<br/>
펜에 대 한 스타일을 지정합니다. 가능한 값 목록을 참조 하세요. 합니다 *nPenStyle* 에 매개 변수를 [CPen](#cpen) 생성자입니다.

*nWidth*<br/>
펜의 너비를 지정합니다.

- 첫 번째 버전의 `CreatePen`, 너비 장치 단위는 1 픽셀 매핑 모드에 관계 없이 항상이 값이 0 인 경우.

- 두 번째 버전의 `CreatePen`이면 *nPenStyle* PS_GEOMETRIC는 너비를 논리 단위로 지정 됩니다. 하는 경우 *nPenStyle* PS_COSMETIC은 너비가 1로 설정 해야 합니다.

*crColor*<br/>
펜에 대 한 RGB 색을 포함합니다.

*pLogBrush*<br/>
가리키는 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) 구조입니다. 경우 *nPenStyle* PS_COSMETIC는 `lbColor` 의 멤버는 `LOGBRUSH` 펜의 색을 지정 하는 구조 및 *lbStyle* 의 멤버는 `LOGBRUSH` 구조 BS_로 설정 되어야 합니다 실선입니다. NPenStyle PS_GEOMETRIC 이면 펜의 브러시 특성을 지정 하려면 모든 멤버를 사용 합니다.

*nStyleCount*<br/>
워드 단위에서 길이 지정 합니다 *lpStyle* 배열입니다. 이 값은 경우에는 0 이어야 *nPenStyle* PS_USERSTYLE 아닙니다.

*lpStyle*<br/>
워드 값의 배열 가리킵니다. 사용자 정의 스타일의 첫 번째 대시의 길이 지정 하는 첫 번째 값, 두 번째 값의 첫 번째 공간 및 등의 길이 지정 합니다. 이 포인터 경우 NULL 이어야 합니다 *nPenStyle* PS_USERSTYLE 아닙니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 메서드가 실패 하는 경우 0입니다.

### <a name="remarks"></a>설명

첫 번째 버전 `CreatePen` 지정 된 스타일, 두께 및 색을 사용 하 여 펜을 초기화 합니다. 펜 이후에 장치 컨텍스트에 대 한 현재 펜으로 선택할 수 있습니다.

1 픽셀 보다 큰 너비는 펜 스타일 PS_NULL, PS_SOLID, 또는 PS_INSIDEFRAME 항상 있어야 합니다.

펜 PS_INSIDEFRAME 스타일 및 색 논리 색상표에서 색을 일치 하지 않는 경우, 펜 디더링된 색으로 그려집니다. 디더링된 색을 사용 하 여 펜을을 만들려면 PS_SOLID 펜 스타일을 사용할 수 없습니다. PS_INSIDEFRAME 스타일은 1 보다 작거나 펜 굵기 이면 PS_SOLID 동일 합니다.

두 번째 버전 `CreatePen` 스타일, 두께 및 브러시 특성이 지정 된 논리 외관 또는 기하학적 펜을 초기화 합니다. 표면적인 펜의 너비는 항상 1입니다. 항상 기하학적 펜의 너비를 전체 단위로 지정 됩니다. 응용 프로그램 논리 펜을 만든 후 선택할 수 있습니다는 펜 장치 컨텍스트로 호출 하 여 합니다 [cdc:: selectobject](../../mfc/reference/cdc-class.md#selectobject) 함수입니다. 펜을 장치 컨텍스트로 선택 선 및 곡선을 그릴 사용할 수 있습니다.

- 하는 경우 *nPenStyle* PS_COSMETIC 이며 PS_USERSTYLE, 항목은 *lpStyle* 배열 스타일 단위로 대시와 공백의 길이 지정 합니다. 스타일 단위 선을 그릴 펜을 사용 하는 장치에 의해 정의 됩니다.

- 하는 경우 *nPenStyle* PS_GEOMETRIC 이며 PS_USERSTYLE, 항목은 *lpStyle* 배열 논리 단위로 대시와 공백의 길이 지정 합니다.

- 하는 경우 *nPenStyle* PS_ALTERNATE는, 스타일 단위는 무시 되 고 다른 모든 픽셀에 설정 됩니다.

호출 해야 응용 프로그램 지정된 펜을 더 이상 필요한 경우는 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수 또는 삭제는 `CPen` 되므로 리소스를 사용에서 하지 않습니다. 개체입니다. 펜 장치 컨텍스트에서 선택 하면 응용 프로그램 펜을 삭제 안 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect

스타일, 두께 및 색에서 가리키는 구조에 지정 된 된 펜 초기화 *lpLogPen*합니다.

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>매개 변수

*lpLogPen*<br/>
Windows를 가리키는 [LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen) 펜에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

1 픽셀 보다 큰 너비는 펜 스타일 PS_NULL, PS_SOLID, 또는 PS_INSIDEFRAME 항상 있어야 합니다.

펜 PS_INSIDEFRAME 스타일 및 색 논리 색상표에서 색을 일치 하지 않는 경우, 펜 디더링된 색으로 그려집니다. PS_INSIDEFRAME 스타일은 1 보다 작거나 펜 굵기 이면 PS_SOLID 동일 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

##  <a name="fromhandle"></a>  CPen::FromHandle

에 대 한 포인터를 반환 합니다.는 `CPen` 개체는 Windows GDI pen 개체에 대 한 핸들을 지정 합니다.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>매개 변수

*hPen*<br/>
`HPEN` Windows GDI 펜에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CPen` 성공 하면 NULL 개체입니다.

### <a name="remarks"></a>설명

`CPen` 개체가 핸들에 연결되지 않은 경우 임시 `CPen` 개체를 만들어 연결합니다. 이 임시 `CPen` 개체는 다음에 응용 프로그램에 유휴 시간 이벤트 루프에서 될 때까지 모든 임시 그래픽 시간이 개체는 삭제만 유효 합니다. 즉, 임시 개체는 하나의 창 메시지를 처리 하는 동안에 유효 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

##  <a name="getextlogpen"></a>  CPen::GetExtLogPen

가져옵니다는 `EXTLOGPEN` 기본 구조입니다.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>매개 변수

*pLogPen*<br/>
가리키는 [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) 펜에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`EXTLOGPEN` 스타일, 두께 및 펜의 브러시 특성 구조를 정의 합니다. 예를 들어 호출 `GetExtLogPen` 펜의 특정 스타일과 일치 하도록 합니다.

펜 특성에 대 한 내용은 Windows SDK의 다음 항목을 참조 하세요.

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

- [ExtCreatePen](/windows/desktop/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>예제

다음 코드 예제에서는 호출 `GetExtLogPen` 펜의 특성을 검색 하 고 다음 같은 색을 사용 하 여 새, 표면적인 펜을 만들 합니다.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

##  <a name="getlogpen"></a>  CPen::GetLogPen

가져옵니다는 `LOGPEN` 기본 구조입니다.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>매개 변수

*pLogPen*<br/>
가리키는 [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) 펜에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`LOGPEN` 구조 스타일, 색 및 펜의 패턴을 정의 합니다.

예를 들어 호출 `GetLogPen` 펜의 특정 스타일과 일치 하도록 합니다.

펜 특성에 대 한 내용은 Windows SDK의 다음 항목을 참조 하세요.

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

### <a name="example"></a>예제

다음 코드 예제에서는 호출 `GetLogPen` 펜의 문자를 검색 하 고 다음 같은 색을 사용 하 여 새, 단색 펜을 만들 합니다.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

##  <a name="operator_hpen"></a>  CPen::operator HPEN

연결 된 Windows GDI 핸들을 가져옵니다는 `CPen` 개체입니다.

```
operator HPEN() const;
```

### <a name="return-value"></a>반환 값

경우 성공 하면 Windows GDI 개체 핸들을 나타내는 `CPen` 개체 고 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 연산자는 캐스팅 연산자를 HPEN 개체의 직접 사용을 지원 합니다.

그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [그래픽 개체](/windows/desktop/gdi/graphic-objects) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>참고자료

[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CBrush 클래스](../../mfc/reference/cbrush-class.md)
