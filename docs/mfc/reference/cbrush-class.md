---
title: CBrush 클래스
ms.date: 11/04/2016
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
ms.openlocfilehash: f2a2e385a9f210b3644d7fade00b72c4befa47ef
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778873"
---
# <a name="cbrush-class"></a>CBrush 클래스

Windows GDI(그래픽 디바이스 인터페이스) 브러시를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CBrush : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CBrush::CBrush](#cbrush)|`CBrush` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CBrush::CreateBrushIndirect](#createbrushindirect)|스타일, 색 및에 지정 된 패턴을 사용 하 여 브러시 초기화 된 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) 구조입니다.|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|장치 독립적 비트맵이 (DIB)로 지정 된 패턴을 사용 하 여 브러시를 초기화 합니다.|
|[CBrush::CreateHatchBrush](#createhatchbrush)|지정 된 교차 무늬 패턴 및 색을 사용 하 여 브러시를 초기화합니다.|
|[CBrush::CreatePatternBrush](#createpatternbrush)|비트맵으로 지정 된 패턴을 사용 하 여 브러시를 초기화 합니다.|
|[CBrush::CreateSolidBrush](#createsolidbrush)|지정 된 단색 브러시를 초기화합니다.|
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|기본 시스템 색상 하는 브러시를 만듭니다.|
|[CBrush::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다는 `CBrush` 개체는 Windows 핸들을 지정한 경우 `HBRUSH` 개체입니다.|
|[CBrush::GetLogBrush](#getlogbrush)|가져옵니다를 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) 구조입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[HBRUSH CBrush::operator](#operator_hbrush)|에 연결 된 Windows 핸들을 반환 합니다 `CBrush` 개체입니다.|

## <a name="remarks"></a>설명

사용 하는 `CBrush` 개체를 생성을 `CBrush` 개체를 전달 하 `CDC` 브러시를 필요로 하는 멤버 함수입니다.

무늬, 또는 무늬 브러시는 단색을 수 있습니다.

에 대 한 자세한 `CBrush`를 참조 하세요 [그래픽 개체](../../mfc/graphic-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cbrush"></a>  CBrush::CBrush

`CBrush` 개체를 생성합니다.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

*crColor*<br/>
RGB 색으로 브러시의 전경색을 지정합니다. 브러시 무늬는 경우이 매개 변수는 빗살 무늬의 색을 지정 합니다.

*nIndex*<br/>
브러시의 빗살 무늬 스타일을 지정합니다. 다음 값 중 하나일 수 있습니다.

- HS_BDIAGONAL 하향 빗살 무늬 (왼쪽에서 오른쪽) 45도 회전

- HS_CROSS 가로 및 세로 격자

- HS_DIAGCROSS 45도 교차 무늬

- HS_FDIAGONAL 상향 빗살 무늬 (왼쪽에서 오른쪽) 45도 회전

- 가로 HS_HORIZONTAL 빗살 무늬

- 세로 HS_VERTICAL 빗살 무늬

*pBitmap*<br/>
가리키는 `CBitmap` 브러시를 그리는 있는 비트맵을 지정 하는 개체입니다.

### <a name="remarks"></a>설명

`CBrush` 생성자 오버 로드는 4입니다. 인수가 없는 생성자는 초기화 되지 않은 생성 `CBrush` 사용 하려면 먼저 초기화 해야 하는 개체입니다.

인수가 없는 생성자를 사용 하는 경우 결과 초기화 해야 합니다 `CBrush` 개체 [CreateSolidBrush](#createsolidbrush)하십시오 [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect)하십시오 [CreatePatternBrush](#createpatternbrush), 또는 [CreateDIBPatternBrush](#createdibpatternbrush)합니다. 인수를 받는 생성자 중 하나를 사용 하는 경우 다음 더 이상 초기화가 필요 합니다. 생성자 인수를 사용 하 여 오류가 발생 하는 경우 생성자는 인수 없이 항상 성공 하는 동안 예외가 throw 할 수 있습니다.

단일 생성자 [COLORREF](/windows/desktop/gdi/colorref) 매개 변수를 지정 된 색으로 단색 브러시를 생성 합니다. 색은 RGB 값을 지정 하 고 WINDOWS에서 RGB 매크로 사용 하 여 생성할 수 있습니다. 8.

두 개의 매개 변수를 사용 하 여 생성자 빗살 무늬 브러시를 생성합니다. 합니다 *nIndex* 빗살 무늬로의 인덱스를 지정 하는 매개 변수입니다. 합니다 *crColor* 매개 변수는 색을 지정 합니다.

사용 하 여 생성자를 `CBitmap` 무늬 브러시를 생성 하는 매개 변수입니다. 매개 변수는 비트맵을 식별합니다. 비트맵을 사용 하 여 만들어진 것으로 간주 됩니다 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)를 [cbitmap:: Createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)하십시오 [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), 또는 [ CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)합니다. 채우기 패턴에 사용할 비트맵의 최소 크기는 8 x 8 픽셀입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

##  <a name="createbrushindirect"></a>  CBrush::CreateBrushIndirect

스타일, 색 및에 지정 된 패턴을 사용 하 여 브러시 초기화 된 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) 구조입니다.

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>매개 변수

*lpLogBrush*<br/>
가리키는 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) 브러시에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

브러시는 장치 컨텍스트에 대 한 현재 브러시로 이후에 선택할 수 있습니다.

브러시 (평면 1, 픽셀당 1 비트로) 단색 비트맵을 사용 하 여 만든 현재 텍스트와 배경 색을 사용 하 여 그려집니다. 0으로 설정 하는 비트를 나타내는 픽셀 현재 텍스트 색을 사용 하 여 그려집니다. 1로 설정 하는 비트를 나타내는 픽셀 현재 배경색을 사용 하 여 그려집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

##  <a name="createdibpatternbrush"></a>  CBrush::CreateDIBPatternBrush

장치 독립적 비트맵이 (DIB)로 지정 된 패턴을 사용 하 여 브러시를 초기화 합니다.

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>매개 변수

*hPackedDIB*<br/>
압축 된 장치 독립적 비트맵이 DIB ()를 포함 하는 전역 메모리 개체를 식별 합니다.

*nUsage*<br/>
지정 여부를 합니다 `bmiColors[]` 의 필드를 [BITMAPINFO](/windows/desktop/api/wingdi/ns-wingdi-tagbitmapinfo) 현재 실현된 논리 팔레트에 명시적 RGB 값 또는 인덱스를 포함 하는 데이터 구조 ("압축 DIB"의 일부). 매개 변수는 다음 값 중 하나 여야 합니다.

- DIB_PAL_COLORS 색은 16 비트 인덱스 배열을 이루어져 있습니다.

- 색상표 DIB_RGB_COLORS 리터럴 RGB 값을 포함합니다.

*lpPackedDIB*<br/>
구성 된 압축된 DIB 가리키는 `BITMAPINFO` 구조 바로 뒤에 비트맵의 픽셀을 정의 하는 바이트 배열입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

브러시는 래스터 작업을 지 원하는 모든 장치 컨텍스트에 대 한 이후에 선택할 수 있습니다.

두 버전에는 DIB를 처리 하는 방식은 다릅니다.

- 첫 번째 버전에서는 DIB에 핸들을 얻기 위해 호출 된 Windows `GlobalAlloc` 함수를 전역 메모리 블록을 할당 하 고 다음 압축된 DIB를 사용 하 여 메모리를 채웁니다.

- 두 번째 버전에서는 필요 없는 호출 `GlobalAlloc` 압축된 DIB에 메모리를 할당 합니다.

압축된 DIB 이루어져는 `BITMAPINFO` 바로 뒤에 비트맵의 픽셀을 정의 하는 바이트 배열 데이터 구조입니다. 채우기 패턴으로 사용 하는 비트맵에는 8 x 8 픽셀 이어야 합니다. 비트맵 보다 큰 경우 Windows는 처음 8 개 행의 왼쪽 위 모퉁이 비트맵의 픽셀 8 개의 열을 해당 하는 비트만을 사용 하 여 채우기 패턴을 만듭니다.

두 가지 색 DIB 패턴 브러시 흑백 장치 컨텍스트로 선택 하는 응용 프로그램, Windows DIB에 지정 된 색 무시 하 고 대신 장치 컨텍스트의 현재 텍스트와 배경 색을 사용 하 여 패턴 브러시를 표시 합니다. 픽셀 DIB (오프셋 0 DIB 색상표에서) 첫 번째 색에 매핑되는 텍스트 색을 사용 하 여 표시 됩니다. 픽셀 (1 색상표의 오프셋)에 두 번째 색에 매핑된 배경색을 사용 하 여 표시 됩니다.

다음 Windows 기능 사용에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

- [CreateDIBPatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrush) (이 함수는 3.0 보다 이전 버전의 Windows 용으로 작성 된 응용 프로그램 호환성을 위해서만 제공 됩니다; 사용을 `CreateDIBPatternBrushPt` 함수입니다.)

- [CreateDIBPatternBrushPt](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrushpt) (Win32 기반 응용 프로그램에 대 한이 기능을 사용할 수 해야 합니다.)

- [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

##  <a name="createhatchbrush"></a>  CBrush::CreateHatchBrush

지정 된 교차 무늬 패턴 및 색을 사용 하 여 브러시를 초기화합니다.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
브러시의 빗살 무늬 스타일을 지정합니다. 다음 값 중 하나일 수 있습니다.

- HS_BDIAGONAL 하향 빗살 무늬 (왼쪽에서 오른쪽) 45도 회전

- HS_CROSS 가로 및 세로 격자

- HS_DIAGCROSS 45도 교차 무늬

- HS_FDIAGONAL 상향 빗살 무늬 (왼쪽에서 오른쪽) 45도 회전

- 가로 HS_HORIZONTAL 빗살 무늬

- 세로 HS_VERTICAL 빗살 무늬

*crColor*<br/>
RGB 색 (의 해치 색)으로 브러시의 전경색을 지정합니다. 참조 [COLORREF](/windows/desktop/gdi/colorref) 자세한 내용은 Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

브러시는 장치 컨텍스트에 대 한 현재 브러시로 이후에 선택할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

##  <a name="createpatternbrush"></a>  CBrush::CreatePatternBrush

비트맵으로 지정 된 패턴을 사용 하 여 브러시를 초기화 합니다.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
비트맵을 식별합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

브러시는 래스터 작업을 지 원하는 모든 장치 컨텍스트에 대 한 이후에 선택할 수 있습니다. 로 식별 되는 비트맵 *pBitmap* 일반적으로 사용 하 여 초기화 되는 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)를 [cbitmap:: Createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap:: LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), 또는 [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) 함수입니다.

채우기 패턴으로 사용 하는 비트맵에는 8 x 8 픽셀 이어야 합니다. 비트맵 보다 큰 경우 Windows는 처음 8 개 행 및 열 비트맵의 왼쪽 위 모서리에 있는 픽셀에 해당 하는 비트만 사용 합니다.

관련된 비트맵을 영향을 주지 않고 패턴 브러시를 삭제할 수 있습니다. 즉, 비트맵 임의 개수의 패턴 브러시를 만드는 데 사용할 수 있습니다.

현재 텍스트와 배경 색을 사용 하는 브러시를 단색 비트맵 (1 색상 평면을 픽셀당 1 비트)를 사용 하 여 만든 그려집니다. 0으로 설정 하는 비트를 나타내는 픽셀은 현재 텍스트 색을 사용 하 여 그려집니다. 1로 설정 하는 비트를 나타내는 픽셀 현재 배경색을 사용 하 여 그려집니다.

사용 하 여에 대 한 자세한 [CreatePatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createpatternbrush)에 Windows 함수를 Windows SDK를 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

##  <a name="createsolidbrush"></a>  CBrush::CreateSolidBrush

지정 된 단색 브러시를 초기화합니다.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>매개 변수

*crColor*<br/>
A [COLORREF](/windows/desktop/gdi/colorref) 브러시의 색을 지정 하는 구조입니다. 색은 RGB 값을 지정 하 고 WINDOWS에서 RGB 매크로 사용 하 여 생성할 수 있습니다. 8.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

브러시는 장치 컨텍스트에 대 한 현재 브러시로 이후에 선택할 수 있습니다.

응용 프로그램이 완료 된 시기 만든 브러시를 사용 하 여 `CreateSolidBrush`, 브러시 장치 컨텍스트에서 선택 해야 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CBrush::CBrush](#cbrush)합니다.

##  <a name="createsyscolorbrush"></a>  CBrush::CreateSysColorBrush

브러시 색을 초기화합니다.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
색 인덱스를 지정합니다. 이 값은 21 창 요소 중 하나를 그리는 데 사용 된 색에 해당 합니다. 참조 [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) 값의 목록을 Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

브러시는 장치 컨텍스트에 대 한 현재 브러시로 이후에 선택할 수 있습니다.

응용 프로그램이 완료 된 시기 만든 브러시를 사용 하 여 `CreateSysColorBrush`, 브러시 장치 컨텍스트에서 선택 해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

##  <a name="fromhandle"></a>  CBrush::FromHandle

에 대 한 포인터를 반환 합니다는 `CBrush` 는 Windows에 대 한 핸들을 지정 하는 경우 개체 [HBRUSH](#operator_hbrush) 개체입니다.

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>매개 변수

*hBrush*<br/>
Windows GDI 브러시에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CBrush` 성공 하면 NULL 개체입니다.

### <a name="remarks"></a>설명

경우는 `CBrush` 개체가 이미 임시 핸들에 연결 되지 않은 `CBrush` 개체를 만들어 연결 합니다. 이 임시 `CBrush` 개체는 다음에 응용 프로그램의 경우 이벤트 루프에 대 한 유휴 시간 까지만 유효 합니다. 이때 임시 그래픽 개체를 모두 삭제 됩니다. 즉, 임시 개체는 한 창 메시지를 처리 하는 동안에 유효 합니다.

그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [그래픽 개체](/windows/desktop/gdi/graphic-objects) Windows SDK에 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CBrush::CBrush](#cbrush)합니다.

##  <a name="getlogbrush"></a>  CBrush::GetLogBrush

검색 하려면이 멤버 함수를 호출 합니다 `LOGBRUSH` 구조입니다.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>매개 변수

*pLogBrush*<br/>
가리키는 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) 브러시에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

함수가 성공 하는 경우 및 *pLogBrush* 유효한 포인터가 반환 값은 버퍼에 저장 된 바이트 수입니다.

함수가 성공 하 고 *pLogBrush* 가 null 인 경우 반환 값은 함수 정보를 저장 하는 데 필요한 바이트 수를 버퍼에 저장 됩니다.

함수가 실패 한 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

`LOGBRUSH` 구조 스타일, 색 및 브러시의 패턴을 정의 합니다.

예를 들어 호출 `GetLogBrush` 특정 색 또는 패턴 비트맵의 일치 하도록 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

##  <a name="operator_hbrush"></a>  HBRUSH CBrush::operator

이 연산자를 사용 하 여 연결 된 Windows GDI 핸들을 가져오려면는 `CBrush` 개체입니다.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>반환 값

경우 성공 하면 Windows GDI 개체 핸들을 나타내는 `CBrush` 개체 고 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 연산자는 캐스팅 연산자를 HBRUSH 개체의 직접 사용을 지원 합니다.

그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [그래픽 개체](/windows/desktop/gdi/graphic-objects) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CBitmap 클래스](../../mfc/reference/cbitmap-class.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)
