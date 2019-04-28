---
title: CGdiObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
ms.openlocfilehash: 1b2b87173bf504455ba314fdd89ffae298cae6a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181992"
---
# <a name="cgdiobject-class"></a>CGdiObject 클래스

비트맵, 영역, 브러시, 펜, 색상표와 글꼴 등 다양한 Windows GDI(그래픽 디바이스 인터페이스) 개체에 기본 클래스를 제공합니다.

## <a name="syntax"></a>구문

```
class CGdiObject : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CGdiObject::CGdiObject](#cgdiobject)|`CGdiObject` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CGdiObject::Attach](#attach)|Windows GDI 개체를 연결 된 `CGdiObject` 개체입니다.|
|[CGdiObject::CreateStockObject](#createstockobject)|Windows의 미리 정의 된 스톡 펜, 브러시 또는 글꼴 중 하나에 대 한 핸들을 검색합니다.|
|[CGdiObject::DeleteObject](#deleteobject)|Windows GDI 개체에 연결 하는 삭제 된 `CGdiObject` 개체에 연결 된 모든 시스템 저장소를 해제 하 여 메모리에서 개체입니다.|
|[CGdiObject::DeleteTempMap](#deletetempmap)|임시 삭제 `CGdiObject` 에서 만든 개체 `FromHandle`합니다.|
|[CGdiObject::Detach](#detach)|Windows GDI 개체를 분리 한 `CGdiObject` 개체 및 Windows GDI 개체에 대 한 핸들을 반환 합니다.|
|[CGdiObject::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CGdiObject` Windows GDI 개체에 대 한 핸들을 지정 된 개체입니다.|
|[CGdiObject::GetObject](#getobject)|입력 한 후에 연결 된 Windows GDI 개체를 설명 하는 데이터를 사용 하 여 버퍼를 `CGdiObject` 개체입니다.|
|[CGdiObject::GetObjectType](#getobjecttype)|GDI 개체의 형식을 검색합니다.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|반환 `m_hObject` 경우가 아니면 **이** 가 NULL 인 경우 NULL 반환 됩니다.|
|[CGdiObject::UnrealizeObject](#unrealizeobject)|브러시의 원점으로 다시 설정 하거나 논리 색상표를 다시 설정 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CGdiObject::operator !=](#operator_neq)|하는 경우 두 GDI 개체가 논리적으로 같지 않은지 확인 합니다.|
|[CGdiObject::operator ==](#operator_eq_eq)|두 GDI 개체가 논리적으로 동일한 지 확인 합니다.|
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|연결된 된 Windows GDI 개체에 대 한 핸들을 검색합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|HBITMAP, HPALETTE, HRGN, HBRUSH, HPEN, 또는 HFONT 포함 된 핸들을이 개체에 연결 합니다.|

## <a name="remarks"></a>설명

되지 만들기는 `CGdiObject` 직접. 대신 개체를 만들면 해당 파생된 클래스 중 하나에서 같은 `CPen` 또는 `CBrush`합니다.

에 대 한 자세한 `CGdiObject`를 참조 하세요 [그래픽 개체](../../mfc/graphic-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="attach"></a>  CGdiObject::Attach

Windows GDI 개체를 연결 된 `CGdiObject` 개체입니다.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>매개 변수

*hObject*<br/>
Windows GDI 개체 (예: HPEN 또는 HBRUSH)에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

첨부 파일에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject

`CGdiObject` 개체를 생성합니다.

```
CGdiObject();
```

### <a name="remarks"></a>설명

되지 만들기는 `CGdiObject` 직접. 대신 개체를 만들면 해당 파생된 클래스 중 하나에서 같은 `CPen` 또는 `Cbrush`합니다.

##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject

미리 정의 된 스톡 Windows GDI 펜, 브러시 또는 글꼴 중 하나에 대 한 핸들을 검색 하 고 GDI 개체를 연결 합니다 `CGdiObject` 개체입니다.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
원하는 주식 개체의 형식을 지정 하는 상수입니다. 매개 변수를 참조 하세요 *fnObject* 에 대 한 [GetStockObject](/windows/desktop/api/wingdi/nf-wingdi-getstockobject) 적절 한 값에 대 한 Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Windows GDI 개체 형식에 있는 클래스를 파생 중 하나를 사용 하 여이 함수 호출 등 해당 `CPen` 주식 펜에 대 한 합니다.

##  <a name="deleteobject"></a>  CGdiObject::DeleteObject

Windows GDI 개체에 연결 된 모든 시스템 저장소를 해제 하 여 메모리에서 연결된 된 Windows GDI 개체를 삭제 합니다.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>반환 값

0이 아닌 GDI 개체를 삭제 했습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

와 연결 된 저장소는 `CGdiObject` 개체가이 호출을 받지 않습니다. 응용 프로그램을 호출 하지 않아야 `DeleteObject` 에 `CGdiObject` 장치 컨텍스트로 선택 되어 있는 개체입니다.

패턴 브러시를 삭제 하면 브러시를 사용 하 여 연결 된 비트맵 삭제 되지 않습니다. 비트맵을 독립적으로 삭제 되어야 합니다.

##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap

자동으로 호출 합니다 `CWinApp` 유휴 시간 처리기 `DeleteTempMap` 임시 삭제 `CGdiObject` 개체에 의해 생성 `FromHandle`합니다.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>설명

`DeleteTempMap` 임시 연결 하 고 Windows GDI 개체를 분리 `CGdiObject` 개체를 삭제 하기 전에 `CGdiObject` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

##  <a name="detach"></a>  CGdiObject::Detach

Windows GDI 개체를 분리 한 `CGdiObject` 개체 및 Windows GDI 개체에 대 한 핸들을 반환 합니다.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>반환 값

`HANDLE` 없습니다 GDI 개체를 연결 하는 경우에 NULL이 고, 그렇지 않으면 Windows GDI 개체 분리 합니다.

##  <a name="fromhandle"></a>  CGdiObject::FromHandle

에 대 한 포인터를 반환 합니다.는 `CGdiObject` Windows GDI 개체에 대 한 핸들을 지정 된 개체입니다.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>매개 변수

*hObject*<br/>
Windows GDI 개체에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CGdiObject` 일시적 또는 영구적 수 있습니다.

### <a name="remarks"></a>설명

경우는 `CGdiObject` Windows GDI 개체에 임시 개체가 이미 연결 되지 않은 `CGdiObject` 개체를 만들어 연결 합니다.

이 임시 `CGdiObject` 개체는 응용 프로그램 임시 그래픽 개체를 모두 삭제 됩니다 이때 해당 이벤트 루프에 대 한 유휴 시간 때까지만 유효 합니다. 다른 방법은 임시 개체가 올바른지만 한 창 메시지를 처리 하는 동안 것입니다.

##  <a name="getobject"></a>  CGdiObject::GetObject

지정된 된 개체를 정의 하는 데이터를 사용 하 여 버퍼를 채웁니다.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>매개 변수

*nCount*<br/>
복사할 바이트 수를 지정 합니다 *lpObject* 버퍼입니다.

*lpObject*<br/>
정보를 수신 하는 사용자가 제공한 버퍼를 가리킵니다.

### <a name="return-value"></a>반환 값

바이트 수를 검색 합니다. 그렇지 않으면 0 경우 오류가 발생합니다.

### <a name="remarks"></a>설명

다음 목록에 표시 된 대로 함수 형식의 그래픽 개체의 형식에 따라 달라 집니다 데이터 구조를 검색 합니다.

|Object|버퍼 유형|
|------------|-----------------|
|`CPen`|[LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen)|
|`CBrush`|[LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)|
|`CFont`|[LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)|
|`CBitmap`|[BITMAP](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap)|
|`CPalette`|WORD|
|`CRgn`|지원 안 함|

개체가 있으면 한 `CBitmap` 개체를 `GetObject` 너비, 높이 및 비트맵의 색 형식 정보를 반환 합니다. 실제 비트를 사용 하 여 검색할 수 있습니다 [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits)합니다.

개체가 `CPalette` 개체를 `GetObject` 색상표의 항목 수를 지정 하는 단어를 검색 합니다. 함수를 검색 하지 않습니다 합니다 [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) 색상표를 정의 하는 구조입니다. 응용 프로그램 호출 하 여 색상표 항목에 대 한 정보를 가져올 수 있습니다 [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)합니다.

##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType

GDI 개체의 형식을 검색합니다.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>반환 값

성공할 경우 개체의 형식 그렇지 않으면 0입니다. 값은 다음 중 하나일 수 있습니다.

- OBJ_BITMAP Bitmap

- OBJ_BRUSH 브러시

- OBJ_FONT Font

- OBJ_PAL 색상표

- OBJ_PEN 펜

- 펜 OBJ_EXTPEN 확장

- OBJ_REGION 지역

- OBJ_DC 장치 컨텍스트

- OBJ_MEMDC 메모리 장치 컨텍스트

- OBJ_METAFILE 메타 파일

- OBJ_METADC 메타 파일 장치 컨텍스트

- OBJ_ENHMETAFILE 확장 메타 파일

- OBJ_ENHMETADC 확장 메타 파일 장치 컨텍스트

##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle

반환 `m_hObject` 경우가 아니면 **이** 가 NULL 인 경우 NULL 반환 됩니다.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>반환 값

연결된 된 Windows GDI 개체;에 대 한 핸들 그렇지 않은 경우 연결 된 개체가 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

일반 핸들 인터페이스 패러다임의 일부 이며 NULL을 핸들에 대해 잘못 되었거나 특수 값으로 하는 경우에 유용 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled)합니다.

##  <a name="m_hobject"></a>  CGdiObject::m_hObject

HBITMAP, HRGN, HBRUSH, HPEN, HPALETTE, 또는 HFONT 포함 된 핸들을이 개체에 연결 합니다.

```
HGDIOBJ m_hObject;
```

##  <a name="operator_neq"></a>  CGdiObject::operator !=

하는 경우 두 GDI 개체가 논리적으로 같지 않은지 확인 합니다.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>매개 변수

*obj*<br/>
기존에 대 한 포인터 `CGdiObject`합니다.

### <a name="remarks"></a>설명

GDI 개체를 왼쪽에서 오른쪽에는 GDI 개체 같음 인지 확인 합니다.

##  <a name="operator_eq_eq"></a>  CGdiObject::operator ==

두 GDI 개체가 논리적으로 동일한 지 확인 합니다.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>매개 변수

*obj*<br/>
기존에 대 한 참조 `CGdiObject`합니다.

### <a name="remarks"></a>설명

GDI 개체를 왼쪽에서 오른쪽에는 GDI 개체와 같은지 확인 합니다.

##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ

연결된 된 Windows GDI 개체;에 대 한 핸들을 검색합니다. 그렇지 않은 경우 연결 된 개체가 없는 경우 NULL입니다.

```
operator HGDIOBJ() const;
```

##  <a name="unrealizeobject"></a>  CGdiObject::UnrealizeObject

브러시의 원점으로 다시 설정 하거나 논리 색상표를 다시 설정 합니다.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

하는 동안 `UnrealizeObject` 멤버 함수는 합니다 `CGdiObject` 클래스에서이 호출 해야 에서만 `CBrush` 또는 `CPalette` 개체입니다.

에 대 한 `CBrush` 개체를 `UnrealizeObject` 시스템이 지정 된 브러시의 원점을 장치 컨텍스트로 선택 되어 다음에 다시 설정 하도록 합니다. 개체가 `CPalette` 개체를 `UnrealizeObject` 시스템이 이전에 실현 되지 않은 것 처럼 색상표를 실현 하도록 합니다. 응용 프로그램 호출 다음에 [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) 시스템 지정된 색상표의 경우 함수는 시스템 색상표에 있는 논리 팔레트를 완전히 다시 매핑합니다.

`UnrealizeObject` 주식 개체를 사용 하 여 함수를 사용 하지 해야 합니다. 합니다 `UnrealizeObject` 새 브러시 origin 설정 될 때마다 함수를 호출 해야 합니다 (이용 하 여 합니다 [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) 함수). `UnrealizeObject` 현재 선택 된 색상표의 모든 디스플레이 컨텍스트를 현재 선택 된 브러시에 대 한 함수를 호출할 수 있어야 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CBitmap 클래스](../../mfc/reference/cbitmap-class.md)<br/>
[CBrush 클래스](../../mfc/reference/cbrush-class.md)<br/>
[CFont 클래스](../../mfc/reference/cfont-class.md)<br/>
[CPalette 클래스](../../mfc/reference/cpalette-class.md)<br/>
[CPen 클래스](../../mfc/reference/cpen-class.md)<br/>
[CRgn 클래스](../../mfc/reference/crgn-class.md)
