---
title: CWindowDC 클래스
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: 55a9ccfc496c95c9e7410cbd5645135ee555ff26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323387"
---
# <a name="cwindowdc-class"></a>CWindowDC 클래스

`CDC`에서 파생됩니다.

## <a name="syntax"></a>구문

```
class CWindowDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|`CWindowDC` 개체를 생성합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CWindowDC::m_hWnd](#m_hwnd)|이 HWND `CWindowDC` 연결 됩니다.|

## <a name="remarks"></a>설명

Windows 함수 호출 [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)생성 시 및 [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) 소멸 시. 즉를 `CWindowDC` 개체의 전체 화면 영역에 액세스 하는 [CWnd](../../mfc/reference/cwnd-class.md) (클라이언트 및 비클라이언트 영역).

사용 하 여 대 한 자세한 내용은 `CWindowDC`를 참조 하세요 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>요구 사항

헤더: afxwin.h

##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC

생성을 `CWindowDC` 의 전체 화면 영역 (클라이언트 및 비클라이언트)에 액세스 하는 개체를 `CWnd` 가리키는 개체가 *pWnd*합니다.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
창의 장치 컨텍스트 개체에 액세스 하는 클라이언트 영역입니다.

### <a name="remarks"></a>설명

Windows 함수를 호출 하는 생성자 [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)합니다.

예외 (형식의 `CResourceException`) 하는 경우 throw 되는 Windows `GetWindowDC` 호출이 실패 합니다. 장치 컨텍스트에 Windows에 이미 할당 모든 사용 가능한 장치 컨텍스트에서 사용할 수 있습니다. 응용 프로그램 Windows 아래에서 언제 든 지 사용할 수 있는 5 개의 일반적인 표시 컨텍스트에 대해 경합 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd

HWND를 `CWnd` 포인터를 사용 하 여 생성에 `CWindowDC` 개체입니다.

```
HWND m_hWnd;
```

### <a name="remarks"></a>설명

`m_hWnd` 보호 된 HWND 형식의 변수가입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CWindowDC::CWindowDC](#cwindowdc)합니다.

## <a name="see-also"></a>참고자료

[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)
