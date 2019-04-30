---
title: CD2DTextFormat 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: fa2f3b663cb5258c64ec0405abacf2e4eedeb987
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396212"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat 클래스

IDWriteTextFormat에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|CD2DTextFormat 개체를 생성합니다.|
|[CD2DTextFormat::~CD2DTextFormat](#_dtorcd2dtextformat)|소멸자입니다. D2D 텍스트 형식으로 개체를 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DTextFormat::Create](#create)|CD2DTextFormat를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextFormat::Destroy](#destroy)|CD2DTextFormat 개체를 제거합니다. (재정의 [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextFormat::Get](#get)|반환 IDWriteTextFormat 인터페이스|
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|글꼴 패밀리 이름을의 복사본을 가져옵니다.|
|[CD2DTextFormat::GetLocaleName](#getlocalename)|로캘 이름의 복사본을 가져옵니다.|
|[CD2DTextFormat::IsValid](#isvalid)|리소스 유효성을 검사 (재정의 [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextFormat::ReCreate](#recreate)|CD2DTextFormat를 다시 만듭니다. (재정의 [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DTextFormat::operator IDWriteTextFormat*](#operator_idwritetextformat_star)|반환 IDWriteTextFormat 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|IDWriteTextFormat 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="_dtorcd2dtextformat"></a>  CD2DTextFormat::~CD2DTextFormat

소멸자입니다. D2D 텍스트 형식으로 개체를 소멸 될 때 호출 됩니다.

```
virtual ~CD2DTextFormat();
```

##  <a name="cd2dtextformat"></a>  CD2DTextFormat::CD2DTextFormat

CD2DTextFormat 개체를 생성합니다.

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*pParentTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

*strFontFamilyName*<br/>
글꼴 패밀리의 이름을 포함 하는 CString 개체입니다.

*fontSize*<br/>
DIP ("장치 독립적 픽셀") 단위로 글꼴의 논리적 크기입니다. DIPequals 1/96 인치입니다.

*fontWeight*<br/>
텍스트 개체의 글꼴 두께 나타내는 값입니다.

*fontStyle*<br/>
텍스트 개체에 대 한 글꼴 스타일을 나타내는 값입니다.

*fontStretch*<br/>
텍스트 개체에 대 한 글꼴 늘이기를 나타내는 값입니다.

*strFontLocale*<br/>
로캘 이름을 포함 하는 CString 개체입니다.

*pFontCollection*<br/>
글꼴 컬렉션 개체에 대 한 포인터입니다. NULL 인 경우 시스템 글꼴 컬렉션을 나타냅니다.

*bAutoDestroy*<br/>
개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.

##  <a name="create"></a>  CD2DTextFormat::Create

CD2DTextFormat를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="destroy"></a>  CD2DTextFormat::Destroy

CD2DTextFormat 개체를 제거합니다.

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextFormat::Get

반환 IDWriteTextFormat 인터페이스

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>반환 값

IDWriteTextFormat 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="getfontfamilyname"></a>  CD2DTextFormat::GetFontFamilyName

글꼴 패밀리 이름을의 복사본을 가져옵니다.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>반환 값

현재 글꼴 패밀리 이름을 포함 하는 CString 개체입니다.

##  <a name="getlocalename"></a>  CD2DTextFormat::GetLocaleName

로캘 이름의 복사본을 가져옵니다.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>반환 값

현재 로캘 이름이 포함 된 CString 개체입니다.

##  <a name="isvalid"></a>  CD2DTextFormat::IsValid

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>반환 값

리소스 유효 하면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_ptextformat"></a>  CD2DTextFormat::m_pTextFormat

IDWriteTextFormat 포인터입니다.

```
IDWriteTextFormat* m_pTextFormat;
```

##  <a name="operator_idwritetextformat_star"></a>  CD2DTextFormat::operator IDWriteTextFormat*

반환 IDWriteTextFormat 인터페이스

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>반환 값

IDWriteTextFormat 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="recreate"></a>  CD2DTextFormat::ReCreate

CD2DTextFormat를 다시 만듭니다.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
