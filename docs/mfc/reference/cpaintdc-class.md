---
title: CPaintDC 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: df1db8a3e65d35f247df7d070119c66b02208815
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373276"
---
# <a name="cpaintdc-class"></a>CPaintDC 클래스

파생 된 디바이스 컨텍스트 클래스 [CDC](../../mfc/reference/cdc-class.md)합니다.

## <a name="syntax"></a>구문

```
class CPaintDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|생성 된 `CPaintDC` 지정 된 연결 [CWnd](../../mfc/reference/cwnd-class.md)합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|포함 된 [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct) 클라이언트 영역을 그리는 데 사용 합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|이 HWND `CPaintDC` 개체를 연결 합니다.|

## <a name="remarks"></a>설명

수행 된 [cwnd:: Beginpaint](../../mfc/reference/cwnd-class.md#beginpaint) 생성 시 및 [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) 소멸 시.

`CPaintDC` 개체에 응답 하는 경우에 사용 수를 [WM_PAINT](/windows/desktop/gdi/wm-paint) 에 일반적으로 메시지에 `OnPaint` 메시지 처리기 멤버 함수입니다.

사용 하 여 대 한 자세한 내용은 `CPaintDC`를 참조 하세요 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC

생성를 `CPaintDC` 개체를 응용 프로그램 창 그리기를 준비 하 고 저장 합니다 [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct) 구조를 [m_ps](#m_ps) 멤버 변수.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
가리키는 합니다 `CWnd` 개체를 `CPaintDC` 개체가 속한.

### <a name="remarks"></a>설명

예외 (형식의 `CResourceException`) 하는 경우 throw 되는 Windows [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) 호출이 실패 합니다. 장치 컨텍스트에 Windows에 이미 할당 모든 사용 가능한 장치 컨텍스트에서 사용할 수 있습니다. 응용 프로그램 Windows 아래에서 언제 든 지 사용할 수 있는 5 개의 일반적인 표시 컨텍스트에 대해 경합 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd

합니다 `HWND` 이 `CPaintDC` 개체를 연결 합니다.

```
HWND m_hWnd;
```

### <a name="remarks"></a>설명

*m_hWnd* 보호 된 변수 형식 HWND입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

##  <a name="m_ps"></a>  CPaintDC::m_ps

`m_ps` 형식의 public 멤버 변수가 [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct)합니다.

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>설명

것은 `PAINTSTRUCT` 전달할을 작성 하 여 [cwnd:: Beginpaint](../../mfc/reference/cwnd-class.md#beginpaint)합니다.

`PAINTSTRUCT` 응용 프로그램에 연결 된 창의 클라이언트 영역을 그리는 데 사용 하는 정보를 포함 한 `CPaintDC` 개체입니다.

통해 장치 컨텍스트 핸들에 액세스할 수 있는지 확인 합니다 `PAINTSTRUCT`합니다. 그러나 핸들을 통해 보다 직접 액세스할 수 있습니다 합니다 `m_hDC` 멤버 변수는 `CPaintDC` CDC에서 상속 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CPaintDC::m_hWnd](#m_hwnd)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
