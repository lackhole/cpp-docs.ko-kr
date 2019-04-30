---
title: CD2DResource 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
ms.openlocfilehash: e2cc6be7119a2df193aa2af415a9c8d4054f537c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396303"
---
# <a name="cd2dresource-class"></a>CD2DResource 클래스

만들고 브러시, 레이어 및 텍스트와 같은 D2D 리소스를 관리 하기 위한 인터페이스를 제공 하는 추상 클래스입니다.

## <a name="syntax"></a>구문

```
class CD2DResource : public CObject;
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[CD2DResource::CD2DResource](#cd2dresource)|CD2DResource 개체를 생성합니다.|
|[CD2DResource::~CD2DResource](#_dtorcd2dresource)|소멸자입니다. D2D 리소스 개체를 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DResource::Create](#create)|CD2DResource를 만듭니다.|
|[CD2DResource::Destroy](#destroy)|CD2DResource 개체를 제거합니다.|
|[CD2DResource::IsValid](#isvalid)|리소스 유효성 검사|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CD2DResource::IsAutoDestroy](#isautodestroy)|자동 검사 플래그를 삭제 합니다.|
|[CD2DResource::ReCreate](#recreate)|CD2DResource를 다시 만듭니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|리소스는 소유자 (CRenderTarget)를 통해 제거 됩니다.|
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|CRenderTarget 부모에 대 한 포인터)|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="_dtorcd2dresource"></a>  CD2DResource::~CD2DResource

소멸자입니다. D2D 리소스 개체를 소멸 될 때 호출 됩니다.

```
virtual ~CD2DResource();
```

##  <a name="cd2dresource"></a>  CD2DResource::CD2DResource

CD2DResource 개체를 생성합니다.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>매개 변수

*pParentTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

*bAutoDestroy*<br/>
개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.

##  <a name="create"></a>  CD2DResource::Create

CD2DResource를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>매개 변수

*pRenderTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="destroy"></a>  CD2DResource::Destroy

CD2DResource 개체를 제거합니다.

```
virtual void Destroy() = 0;
```

##  <a name="isautodestroy"></a>  CD2DResource::IsAutoDestroy

자동 검사 플래그를 삭제 합니다.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>반환 값

개체 소유자;에 의해 소멸 되 면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="isvalid"></a>  CD2DResource::IsValid

리소스 유효성 검사

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>반환 값

리소스 유효 하면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_bisautodestroy"></a>  CD2DResource::m_bIsAutoDestroy

리소스는 소유자 (CRenderTarget)를 통해 제거 됩니다.

```
BOOL m_bIsAutoDestroy;
```

##  <a name="m_pparenttarget"></a>  CD2DResource::m_pParentTarget

CRenderTarget 부모에 대 한 포인터)

```
CRenderTarget* m_pParentTarget;
```

##  <a name="recreate"></a>  CD2DResource::ReCreate

CD2DResource를 다시 만듭니다.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*pRenderTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
