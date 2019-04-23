---
title: CPalette 클래스
ms.date: 11/04/2016
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
ms.openlocfilehash: f0105a8ee33a57f7431a9c6a97b4b132f291f42a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58770814"
---
# <a name="cpalette-class"></a>CPalette 클래스

Windows 색상표를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPalette : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPalette::CPalette](#cpalette)|생성 된 `CPalette` 연결 된 Windows 색상표가 사용 하 여 개체입니다. 초기화 해야 합니다는 `CPalette` 사용 하기 전에 초기화 멤버 함수 중 하나를 사용 하 여 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPalette::AnimatePalette](#animatepalette)|대체 항목으로 식별 논리 색상표에는 `CPalette` 개체입니다. 응용 프로그램 않아도 해당 클라이언트 영역을 업데이트 Windows 시스템 색상표에 새 항목을 즉시 매핑하기 때문입니다.|
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|장치 컨텍스트에 대 한 하프톤 팔레트를 만들고 연결 하는 `CPalette` 개체입니다.|
|[CPalette::CreatePalette](#createpalette)|Windows 색상표를 만들고 연결 하는 `CPalette` 개체입니다.|
|[CPalette::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CPalette` Windows 색상표 개체에 대 한 핸들을 지정 하는 경우 개체입니다.|
|[CPalette::GetEntryCount](#getentrycount)|논리 색상표의 색상표 항목의 수를 검색 합니다.|
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|논리 팔레트 색 값을 가장 잘 맞는 항목의 인덱스를 반환 합니다.|
|[CPalette::GetPaletteEntries](#getpaletteentries)|논리 색상표의 색상표 항목의 범위를 검색합니다.|
|[CPalette::ResizePalette](#resizepalette)|지정 된 논리 색상표의 크기를 변경 합니다 `CPalette` 항목 수가 지정 된 개체입니다.|
|[CPalette::SetPaletteEntries](#setpaletteentries)|논리 색상표에 있는 항목의 범위에서 RGB 색상 값 및 플래그를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[HPALETTE CPalette::operator](#operator_hpalette)|반환 된 HPALETTE 연결할는 `CPalette`합니다.|

## <a name="remarks"></a>설명

색상표 색 출력 장치 (예: 디스플레이 장치)는 응용 프로그램 사이의 인터페이스를 제공합니다. 인터페이스는 심각 하 게 다른 응용 프로그램에서 표시 되는 색상을 방해 하지 않고 출력 장치의 색 기능의 활용 하기 위해 응용 프로그램을 허용 합니다. Windows 사용 되는 색을 결정 하는 응용 프로그램의 논리 색상표 (필요한 색 목록) 및 (사용할 수 있는 색을 정의 함)는 시스템 색상표를 사용 합니다.

`CPalette` 개체에서 참조 하는 색상표를 조작에 대 한 개체는 멤버 함수를 제공 합니다. 생성 된 `CPalette` 개체 및 실제 색상표, 그래픽 장치 인터페이스 (GDI) 개체를 만들고 해당 항목 및 기타 속성을 조작 하는 멤버 함수를 사용 합니다.

사용 하 여 대 한 자세한 내용은 `CPalette`를 참조 하세요 [그래픽 개체](../../mfc/graphic-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="animatepalette"></a>  CPalette::AnimatePalette

항목에 연결 된 논리 색상표의 대체 된 `CPalette` 개체입니다.

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>매개 변수

*nStartIndex*<br/>
애니메이션을 적용할 수 있도록 색상표에 첫 번째 항목을 지정 합니다.

*nNumEntries*<br/>
애니메이션을 적용할 수 있도록 색상표에 항목 수를 지정 합니다.

*lpPaletteColors*<br/>
배열의 첫 번째 멤버를 가리킵니다 [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) 구조에서 식별 된 색상표 항목을 바꾸려면 *nStartIndex* 하 고 *nNumEntries*합니다.

### <a name="remarks"></a>설명

응용 프로그램을 호출 하면 `AnimatePalette`, Windows 시스템 색상표에 새 항목을 즉시 매핑되기 때문에 해당 클라이언트 영역을 업데이트 필요가 없습니다.

`AnimatePalette` PC_RESERVED 플래그가 해당 설정 된 함수 항목에만 변경 됩니다 `palPaletteEntry` 의 멤버는 [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) 구조에 연결 된를 `CPalette` 개체입니다. 이 구조에 대 한 자세한 내용은 Windows SDK의 LOGPALETTE를 참조 하세요.

##  <a name="cpalette"></a>  CPalette::CPalette

`CPalette` 개체를 생성합니다.

```
CPalette();
```

### <a name="remarks"></a>설명

호출 하기 전에 개체에 연결 된 색상표가 `CreatePalette` 하나를 연결 합니다.

##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette

장치 컨텍스트에 대 한 하프톤 팔레트를 만듭니다.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
장치 컨텍스트를 식별합니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램을 장치 컨텍스트에의 늘이기 모드 하프톤으로 설정 된 경우 하프톤 팔레트를 만들어야 합니다. 반환한 논리 하프톤 팔레트를 [CreateHalftonePalette](/windows/desktop/api/wingdi/nf-wingdi-createhalftonepalette) 멤버 함수는 다음 선택 하 고 장치 컨텍스트를 실현 합니다 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) 또는 [ StretchDIBits](/windows/desktop/api/wingdi/nf-wingdi-stretchdibits) 함수를 호출 합니다.

에 대 한 자세한 내용은 Windows SDK를 참조 하세요 `CreateHalftonePalette` 고 `StretchDIBits`입니다.

##  <a name="createpalette"></a>  CPalette::CreatePalette

초기화를 `CPalette` 에 연결 하는 Windows 논리 색상표를 만드는 개체는 `CPalette` 개체입니다.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>매개 변수

*lpLogPalette*<br/>
가리키는 [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) 논리 색상표의 색에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.는 `LOGPALETTE` 구조입니다.

##  <a name="fromhandle"></a>  CPalette::FromHandle

에 대 한 포인터를 반환 합니다.는 `CPalette` Windows 색상표 개체에 대 한 핸들을 지정 하는 경우 개체입니다.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>매개 변수

*hPalette*<br/>
Windows GDI 색상표 핸들입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CPalette` 성공 하면 NULL 개체입니다.

### <a name="remarks"></a>설명

경우는 `CPalette` 개체가 임시, Windows 색상표에 이미 연결 되지 않은 `CPalette` 개체를 만들어 연결 합니다. 이 임시 `CPalette` 개체는 다음에 응용 프로그램에 유휴 시간 이벤트 루프에서 될 때까지 모든 임시 그래픽 시간이 개체는 삭제만 유효 합니다. 즉, 임시 개체는 한 창 메시지를 처리 하는 동안에 유효 합니다.

##  <a name="getentrycount"></a>  CPalette::GetEntryCount

지정 된 논리 색상표에 있는 항목의 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
int GetEntryCount();
```

### <a name="return-value"></a>반환 값

논리 색상표에 있는 엔트리의 수입니다.

##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex

지정 된 색 값을 가장 잘 맞는 논리 팔레트에서 항목의 인덱스를 반환 합니다.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>매개 변수

*crColor*<br/>
일치 시킬 색을 지정 합니다.

### <a name="return-value"></a>반환 값

논리 색상표에 있는 항목의 인덱스입니다. 항목을 거의 대부분의 지정된 된 색과 일치 하는 색이 포함 됩니다.

##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries

논리 색상표의 색상표 항목의 범위를 검색합니다.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>매개 변수

*nStartIndex*<br/>
검색할 논리 색상표의 첫 번째 항목을 지정 합니다.

*nNumEntries*<br/>
검색할 논리 색상표의 항목 수를 지정 합니다.

*lpPaletteColors*<br/>
배열을 가리킵니다 [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) 색상표 항목을 수신 하도록 데이터 구조입니다. 배열에 지정 된 대로 이상의 데이터 구조에 포함 되어야 *nNumEntries*합니다.

### <a name="return-value"></a>반환 값

논리 색상표;에서 검색 된 항목의 수 함수가 실패 하는 경우 0입니다.

##  <a name="operator_hpalette"></a>  CPalette::operator HPALETTE

이 연산자를 사용 하 여 연결 된 Windows GDI 핸들을 가져오려면는 `CPalette` 개체입니다.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>반환 값

경우 성공 하면 Windows GDI 개체 핸들을 나타내는 `CPalette` 개체 고 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 연산자는 캐스팅 연산자를 HPALETTE 개체의 직접 사용을 지원 합니다.

그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [그래픽 개체](/windows/desktop/gdi/graphic-objects) Windows SDK에 있습니다.

##  <a name="resizepalette"></a>  CPalette::ResizePalette

연결할 논리 색상표의 크기를 변경 합니다 `CPalette` 개체를 지정 된 항목 수가 *nNumEntries*합니다.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>매개 변수

*nNumEntries*<br/>
크기가 조정 된 후에 색상표의 항목 수를 지정 합니다.

### <a name="return-value"></a>반환 값

색상표를 성공적으로 크기가 조정 되었습니다. 0이 아닌 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램을 호출 하는 경우 `ResizePalette` 색상표의 크기를 줄이려면 크기가 조정 된 색상표에 남아 있는 항목은 변경 되지 않았습니다. 응용 프로그램을 호출 하는 경우 `ResizePalette` 색상표를 확대 하려면 추가 색상표 항목을 검정으로 (빨강, 녹색 및 파랑 값은 모든 0), 설정 및 모든 추가 항목에 대 한 플래그를 0으로 설정 됩니다.

Windows API에 대 한 자세한 내용은 `ResizePalette`를 참조 하세요 [ResizePalette](/windows/desktop/api/wingdi/nf-wingdi-resizepalette) Windows SDK에 있습니다.

##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries

논리 색상표에 있는 항목의 범위에서 RGB 색상 값 및 플래그를 설정합니다.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>매개 변수

*nStartIndex*<br/>
설정할 논리 색상표의 첫 번째 항목을 지정 합니다.

*nNumEntries*<br/>
설정할 논리 색상표의 항목 수를 지정 합니다.

*lpPaletteColors*<br/>
배열을 가리킵니다 [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) 색상표 항목을 수신 하도록 데이터 구조입니다. 배열에 지정 된 대로 이상의 데이터 구조에 포함 되어야 *nNumEntries*합니다.

### <a name="return-value"></a>반환 값

항목 수가 설정에서 논리 팔레트; 함수가 실패 하는 경우 0입니다.

### <a name="remarks"></a>설명

응용 프로그램을 호출할 때 논리 팔레트를 장치 컨텍스트로 선택 됩니다 `SetPaletteEntries`, 응용 프로그램이 호출 될 때까지 변경 내용이 적용 되지 것입니다 [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)합니다.

Windows 구조에 대 한 자세한 내용은 `PALETTEENTRY`를 참조 하세요 [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPalette::GetPaletteEntries](#getpaletteentries)<br/>
[CPalette::SetPaletteEntries](#setpaletteentries)
