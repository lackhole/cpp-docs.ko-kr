---
title: CClientDC 클래스
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: a67af5d7d82b8bd7d0490d4ae6f9535bf3283ea2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206626"
---
# <a name="cclientdc-class"></a>CClientDC 클래스

Windows 함수 호출을 맡고 [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) 생성 시 및 [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) 소멸 시.

## <a name="syntax"></a>구문

```
class CClientDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|생성을 `CClientDC` 에 연결 하는 개체는 `CWnd`합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CClientDC::m_hWnd](#m_hwnd)|이 창의 HWND `CClientDC` 유효 합니다.|

## <a name="remarks"></a>설명

즉, 연결 된 장치 컨텍스트는 `CClientDC` 개체가 창의 클라이언트 영역입니다.

에 대 한 자세한 `CClientDC`를 참조 하세요 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cclientdc"></a>  CClientDC::CClientDC

생성을 `CClientDC` 의 클라이언트 영역에 액세스 하는 개체를 [CWnd](../../mfc/reference/cwnd-class.md) 가리키는 *pWnd*합니다.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
창의 장치 컨텍스트 개체를 액세스 하는 클라이언트 영역입니다.

### <a name="remarks"></a>설명

Windows 함수를 호출 하는 생성자 [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc)합니다.

예외 (형식의 `CResourceException`) 하는 경우 throw 되는 Windows `GetDC` 호출이 실패 합니다. 장치 컨텍스트에 Windows에 이미 할당 모든 사용 가능한 장치 컨텍스트에서 사용할 수 있습니다. 응용 프로그램 Windows 아래에서 언제 든 지 사용할 수 있는 5 개의 일반적인 표시 컨텍스트에 대해 경합 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CClientDC::m_hWnd

`HWND` 의 합니다 `CWnd` 생성 하는 데 대 한 포인터를 `CClientDC` 개체입니다.

```
HWND m_hWnd;
```

### <a name="remarks"></a>설명

*m_hWnd* 보호 된 변수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CClientDC::CClientDC](#cclientdc)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)
