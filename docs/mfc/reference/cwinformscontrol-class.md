---
title: CWinFormsControl 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: c1c7a394317fefba7911e9500126919e83389f20
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504671"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl 클래스

Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공합니다.

## <a name="syntax"></a>구문

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>매개 변수

*TManagedControl*<br/>
MFC 응용 프로그램에 표시 되는.NET Framework Windows Forms 컨트롤입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows Forms 컨트롤 래퍼 개체를 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Windows Forms 컨트롤을 MFC 컨테이너에 만듭니다.|
|[CWinFormsControl::GetControl](#getcontrol)|Windows Forms 컨트롤에 대 한 포인터를 검색합니다.|
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows Forms 컨트롤에 대 한 핸들을 검색합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CWinFormsControl::operator -&gt;](#operator_-_gt)|대체 [CWinFormsControl::GetControl](#getcontrol) 식에 있습니다.|
|[CWinFormsControl::operator TManagedControl^](#operator_tmanagedcontrol)|Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.|

## <a name="remarks"></a>설명

`CWinFormsControl` 클래스는 Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공 합니다.

Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

MFC 코드 창 핸들 캐시 하지 않습니다 (일반적으로 저장 `m_hWnd`). 일부 Windows Forms 컨트롤 속성을 필요로 하는 기본 Win32 `Window` 제거 하 고 사용 하 여 다시 `DestroyWindow` 고 `CreateWindow`입니다. MFC Windows Forms 구현 처리 합니다 `Destroy` 및 `Create` 업데이트할 컨트롤의 이벤트는 `m_hWnd` 멤버입니다.

> [!NOTE]
>  MFC Windows Forms 통합 (AFXDLL 정의 되어 있는) MFC를 사용 하 여 동적으로 링크 하는 프로젝트에만 작동 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h

##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl

Windows Forms 컨트롤을 MFC 컨테이너에 만듭니다.

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>매개 변수

*pType*<br/>
만들려는 컨트롤의 데이터 형식입니다. 이어야 합니다는 [형식](/dotnet/api/system.type) 데이터 형식입니다.

*dwStyle*<br/>
컨트롤에 적용할 창 스타일입니다. 조합을 지정할 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다. 현재, 다음과 같은 스타일만 지원 됩니다. WS_TABSTOP, WS_VISIBLE, WS_DISABLED 및 WS_GROUP 합니다.

*rect*<br/>
A [RECT 구조체](/windows/desktop/api/windef/ns-windef-tagrect) 컨트롤의 왼쪽 및 오른쪽 아래 모퉁이의 좌표를 정의 하는 (첫 번째 오버 로드만).

*nPlaceHolderID*<br/>
리소스 편집기에서 배치 하는 정적 자리 표시자 컨트롤의 핸들입니다. 새로 만든된 Windows Forms 컨트롤을 해당 위치, z-순서 및 스타일 가정 하 고 정적 컨트롤을 대체 (두 번째 오버 로드만).

*pParentWnd*<br/>
부모 창에 대 한 포인터입니다.

*nID*<br/>
새로 만든된 컨트롤에 할당할 리소스 ID.

*pControl*<br/>
연결 하는 Windows Forms 컨트롤의 인스턴스를 [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) 개체 (네 번째 오버 로드만).

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값을 반환 합니다. 실패 하면 0을 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 MFC 컨테이너에서.NET Framework Windows Forms 컨트롤을 인스턴스화합니다.

메서드의 첫 번째 오버 로드는.NET Framework 데이터 형식을 허용 *pType* MFC는이 형식의 새 개체를 인스턴스화할 수 있도록 합니다. *pType* 이어야 합니다는 [형식](/dotnet/api/system.type) 데이터 형식입니다.

메서드의 두 번째 오버 로드에 따라 Windows Forms 컨트롤을 만듭니다는 `TManagedControl` 템플릿 매개 변수에 `CWinFormsControl` 클래스입니다. 크기와 컨트롤의 위치를 기반으로 합니다 `RECT` 메서드에 전달 하는 구조입니다. 만 *dwStyle* 스타일에 대 한 중요 합니다.

메서드의 세 번째 오버 로드를 제거 하 고 해당 위치, z-순서 및 스타일을 담당 합니다. 정적 컨트롤을 대체 하는 Windows Forms 컨트롤을 만듭니다. 정적 컨트롤은 Windows Forms 컨트롤에 대 한 자리 표시자 역할만합니다. 컨트롤을 만들 때이 오버 로드에서 스타일을 결합 *dwStyle* 정적 컨트롤의 리소스 스타일을 사용 합니다.

메서드의 네 번째 오버 로드를 사용 하면 이미 인스턴스화된 Windows Forms 컨트롤에 전달할 *pControl* 을 MFC 래핑하는 합니다. 동일한 형식 이어야 합니다는 `TManagedControl` 템플릿 매개 변수에 `CWinFormsControl` 클래스입니다.

참조 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 샘플 Windows Form을 사용 하 여 제어 합니다.

##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl

MFC Windows Forms 컨트롤 래퍼 개체를 생성 합니다.

```
CWinFormsControl();
```

### <a name="remarks"></a>설명

Windows Forms 컨트롤을 호출할 때 인스턴스화됩니다 [CWinFormsControl::CreateManagedControl](#createmanagedcontrol)합니다.

##  <a name="getcontrol"></a>  CWinFormsControl::GetControl

Windows Forms 컨트롤에 대 한 포인터를 검색합니다.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>반환 값

Windows Forms 컨트롤에 대 한 포인터를 반환합니다.

### <a name="example"></a>예제

  참조 [CWinFormsControl::CreateManagedControl](#createmanagedcontrol)합니다.

##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle

Windows Forms 컨트롤에 대 한 핸들을 검색합니다.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>반환 값

Windows Forms 컨트롤에 대 한 핸들을 반환합니다.

### <a name="remarks"></a>설명

`GetControlHandle` .NET Framework 컨트롤 속성에 저장 된 창 핸들을 반환 하는 도우미 메서드입니다. 창 핸들 값을를 복사할 [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) 호출 하는 동안 [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach)합니다.

##  <a name="operator_-_gt"></a>  CWinFormsControl::operator -&gt;

대체 [CWinFormsControl::GetControl](#getcontrol) 식에 있습니다.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>설명

이 연산자를 대체 하는 편리한 구문을 제공 `GetControl` 식에 있습니다.

Windows Forms에 대 한 자세한 내용은 참조 하세요. [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl^

Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>설명

이 연산자가 전달 `CWinFormsControl<TManagedControl>` Windows Forms 컨트롤에 대 한 포인터를 받아들이는 함수입니다.

## <a name="see-also"></a>참고자료

[CWinFormsDialog 클래스](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md)
