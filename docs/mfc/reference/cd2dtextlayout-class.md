---
title: CD2DTextLayout 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: ca89d12c6aeed33be740aa9f999e7c11d6c32056
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396186"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout 클래스

IDWriteTextLayout에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|CD2DTextLayout 개체를 생성합니다.|
|[CD2DTextLayout::~CD2DTextLayout](#_dtorcd2dtextlayout)|소멸자입니다. D2D 텍스트 레이아웃 개체를 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DTextLayout::Create](#create)|CD2DTextLayout를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::Destroy](#destroy)|CD2DTextLayout 개체를 제거합니다. (재정의 [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout::Get](#get)|반환 IDWriteTextLayout 인터페이스|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|지정된 된 위치에서 텍스트의 글꼴 패밀리 이름을 복사합니다.|
|[CD2DTextLayout::GetLocaleName](#getlocalename)|지정된 된 위치에서 텍스트의 로캘 이름을 가져옵니다.|
|[CD2DTextLayout::IsValid](#isvalid)|리소스 유효성을 검사 (재정의 [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextLayout::ReCreate](#recreate)|CD2DTextLayout를 다시 만듭니다. (재정의 [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|지정 된 텍스트 범위 내의 텍스트에 대 한 집합으로 끝나는 글꼴 패밀리 이름|
|[CD2DTextLayout::SetLocaleName](#setlocalename)|지정 된 텍스트 범위 내의 텍스트에 대 한 로캘 이름을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DTextLayout::operator IDWriteTextLayout*](#operator_idwritetextlayout_star)|반환 IDWriteTextLayout 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|IDWriteTextLayout 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="_dtorcd2dtextlayout"></a>  CD2DTextLayout::~CD2DTextLayout

소멸자입니다. D2D 텍스트 레이아웃 개체를 소멸 될 때 호출 됩니다.

```
virtual ~CD2DTextLayout();
```

##  <a name="cd2dtextlayout"></a>  CD2DTextLayout::CD2DTextLayout

CD2DTextLayout 개체를 생성합니다.

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*pParentTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

*strText*<br/>
만든 새 CD2DTextLayout 개체를 만들 문자열을 포함 하는 CString 개체입니다.

*textFormat*<br/>
문자열에 적용할 형식을 포함 하는 CString 개체입니다.

*sizeMax*<br/>
레이아웃 상자의 크기입니다.

*bAutoDestroy*<br/>
개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.

##  <a name="create"></a>  CD2DTextLayout::Create

CD2DTextLayout를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="destroy"></a>  CD2DTextLayout::Destroy

CD2DTextLayout 개체를 제거합니다.

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextLayout::Get

반환 IDWriteTextLayout 인터페이스

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>반환 값

IDWriteTextLayout 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="getfontfamilyname"></a>  CD2DTextLayout::GetFontFamilyName

지정된 된 위치에서 텍스트의 글꼴 패밀리 이름을 복사합니다.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>매개 변수

*currentPosition*<br/>
검사할 텍스트의 위치입니다.

*textRange*<br/>
현재 위치에 지정 된 위치에서 텍스트와 같은 텍스트 범위 서식 지정. 이 글꼴 패밀리 이름으로 제한 되지 않음, 지정 된 위치와 동일한 서식을 것을 의미 합니다.

### <a name="return-value"></a>반환 값

현재 글꼴 패밀리 이름을 포함 하는 CString 개체입니다.

##  <a name="getlocalename"></a>  CD2DTextLayout::GetLocaleName

지정된 된 위치에서 텍스트의 로캘 이름을 가져옵니다.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>매개 변수

*currentPosition*<br/>
위치를 검사 하는 텍스트입니다.

*textRange*<br/>
현재 위치에 지정 된 위치에서 텍스트와 같은 텍스트 범위 서식 지정. 이 실행 로캘 이름으로 제한 되지 않음, 지정 된 위치와 정확한 서식이 있는 것을 의미 합니다.

### <a name="return-value"></a>반환 값

현재 로캘 이름이 포함 된 CString 개체입니다.

##  <a name="isvalid"></a>  CD2DTextLayout::IsValid

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>반환 값

리소스 유효 하면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_ptextlayout"></a>  CD2DTextLayout::m_pTextLayout

IDWriteTextLayout 포인터입니다.

```
IDWriteTextLayout* m_pTextLayout;
```

##  <a name="operator_idwritetextlayout_star"></a>  CD2DTextLayout::operator IDWriteTextLayout*

반환 IDWriteTextLayout 인터페이스

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>반환 값

IDWriteTextLayout 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="recreate"></a>  CD2DTextLayout::ReCreate

CD2DTextLayout를 다시 만듭니다.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="setfontfamilyname"></a>  CD2DTextLayout::SetFontFamilyName

지정 된 텍스트 범위 내의 텍스트에 대 한 집합으로 끝나는 글꼴 패밀리 이름

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>매개 변수

*pwzFontFamilyName*<br/>
TextRange에 지정한 범위 내에서 전체 텍스트 문자열에 적용 되는 글꼴 패밀리 이름

*textRange*<br/>
이 변경 적용 되는 텍스트 범위

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환 합니다.

##  <a name="setlocalename"></a>  CD2DTextLayout::SetLocaleName

지정 된 텍스트 범위 내의 텍스트에 대 한 로캘 이름을 설정합니다.

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>매개 변수

*pwzLocaleName*<br/>
Null로 끝나는 로캘 이름 문자열을

*textRange*<br/>
이 변경 적용 되는 텍스트 범위

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환 합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
