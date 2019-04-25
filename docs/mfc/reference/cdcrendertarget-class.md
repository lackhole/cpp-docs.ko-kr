---
title: CDCRenderTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 70169d2b89d9ea657898f7a96dea27556023d4e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168175"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget 클래스

ID2D1DCRenderTarget에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|CDCRenderTarget 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDCRenderTarget::Attach](#attach)|기존 연결 개체를 대상 인터페이스를 렌더링 합니다.|
|[CDCRenderTarget::BindDC](#binddc)|렌더링 대상을 그리기 명령을 실행 하는 장치 컨텍스트에 바인딩합니다.|
|[CDCRenderTarget::Create](#create)|CDCRenderTarget을 만듭니다.|
|[CDCRenderTarget::Detach](#detach)|개체의 렌더링 대상 인터페이스를 분리합니다.|
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|반환 ID2D1DCRenderTarget 인터페이스|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CDCRenderTarget::operator ID2D1DCRenderTarget*](#operator_id2d1dcrendertarget_star)|반환 ID2D1DCRenderTarget 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget 개체에 대 한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="attach"></a>  CDCRenderTarget::Attach

기존 연결 개체를 대상 인터페이스를 렌더링 합니다.

```
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>매개 변수

*pTarget*<br/>
기존 렌더링 대상 인터페이스입니다. NULL 일 수 없습니다.

##  <a name="binddc"></a>  CDCRenderTarget::BindDC

렌더링 대상을 그리기 명령을 실행 하는 장치 컨텍스트에 바인딩합니다.

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*dc*<br/>
렌더링 대상의 그리기 명령을 실행 하는 장치 컨텍스트

*rect*<br/>
렌더링 대상의 연결 된 장치 컨텍스트 (HDC)에 대 한 핸들의 크기

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="cdcrendertarget"></a>  CDCRenderTarget::CDCRenderTarget

CDCRenderTarget 개체를 생성합니다.

```
CDCRenderTarget();
```

##  <a name="create"></a>  CDCRenderTarget::Create

CDCRenderTarget을 만듭니다.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>매개 변수

*props*<br/>
렌더링 모드, 픽셀 형식, 원격 옵션, DPI 정보 및 하드웨어 렌더링에 필요한 최소 DirectX 지원 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="detach"></a>  CDCRenderTarget::Detach

개체의 렌더링 대상 인터페이스를 분리합니다.

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>반환 값

분리에 대 한 포인터는 대상 인터페이스를 렌더링 합니다.

##  <a name="getdcrendertarget"></a>  CDCRenderTarget::GetDCRenderTarget

반환 ID2D1DCRenderTarget 인터페이스

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>반환 값

ID2D1DCRenderTarget 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="m_pdcrendertarget"></a>  CDCRenderTarget::m_pDCRenderTarget

ID2D1DCRenderTarget 개체에 대 한 포인터입니다.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

##  <a name="operator_id2d1dcrendertarget_star"></a>  CDCRenderTarget::operator ID2D1DCRenderTarget*

반환 ID2D1DCRenderTarget 인터페이스

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>반환 값

ID2D1DCRenderTarget 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
