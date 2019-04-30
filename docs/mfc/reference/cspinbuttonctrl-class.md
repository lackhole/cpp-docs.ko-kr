---
title: CSpinButtonCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
ms.openlocfilehash: 6f864a37c46158ab98776cd96d9f50d7cfaeb13d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324404"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl 클래스

Windows의 공용 스핀 단추 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|`CSpinButtonCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSpinButtonCtrl::Create](#create)|스핀 단추 컨트롤을 만들고 연결 하는 `CSpinButtonCtrl` 개체입니다.|
|[CSpinButtonCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 스핀 단추 컨트롤을 만들고 연결 하는 `CSpinButtonCtrl` 개체입니다.|
|[CSpinButtonCtrl::GetAccel](#getaccel)|스핀 단추 컨트롤에 대 한 가속 정보를 검색합니다.|
|[CSpinButtonCtrl::GetBase](#getbase)|스핀 단추 컨트롤에 대 한 현재 자료를 검색합니다.|
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|현재 버디 창에 대 한 포인터를 검색합니다.|
|[CSpinButtonCtrl::GetPos](#getpos)|스핀 단추 컨트롤의 현재 위치를 검색합니다.|
|[CSpinButtonCtrl::GetRange](#getrange)|스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 검색합니다.|
|[CSpinButtonCtrl::SetAccel](#setaccel)|스핀 단추 컨트롤에 대 한 가속을 설정합니다.|
|[CSpinButtonCtrl::SetBase](#setbase)|스핀 단추 컨트롤을 설정 합니다.|
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|스핀 단추 컨트롤의 버디 창을 설정입니다.|
|[CSpinButtonCtrl::SetPos](#setpos)|컨트롤에 대 한 현재 위치를 설정합니다.|
|[CSpinButtonCtrl::SetRange](#setrange)|스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 설정합니다.|

## <a name="remarks"></a>설명

"스핀 단추 컨트롤이" (을 up-down 컨트롤이 라고도 함)는 사용자가 클릭 하 여 증가 시키거나 스크롤 위치 또는 첨부 컨트롤에 표시 되는 번호와 같은 값을 감소 시킬 수 있는 화살표 단추 쌍. 스핀 단추 컨트롤을 사용 하 여 연결 된 값을 현재 위치를 라고 합니다. 스핀 단추 컨트롤은 "버디 창입니다." 라는 도우미 컨트롤을 사용 하 여 가장 많이 사용

이 컨트롤 (및 따라서는 `CSpinButtonCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.

사용자에 게 스핀 단추 컨트롤 및 해당 버디 창 처럼 표시 됩니다, 단일 컨트롤입니다. 스핀 단추 컨트롤을 자동으로 자체의 버디 창 옆에 있는 놓고 현재 위치로 버디 창 캡션에 자동으로 설정를 지정할 수 있습니다. 편집 컨트롤을 사용 하 여 숫자 입력에 대 한 사용자에 게 프롬프트 스핀 단추 컨트롤을 사용할 수 있습니다.

위쪽 화살표를 클릭 하는 현재 위치를 최대 방향으로 이동한 최소 방향으로 현재 위치를 이동 아래쪽 화살표를 클릭 합니다. 기본적으로 최소값은 100이 고 최대값은 0입니다. 최소 설정을 설정 (예를 들어 경우 기본 설정이 사용 됩니다), 위쪽 화살표 감소를 클릭 하는 최대값 보다 큽니다. 언제 든 지 위치 값 및 아래쪽 화살표를 클릭 늘립니다.

스핀 단추 컨트롤이 버디 창 없이 간소화 된 스크롤 막대의 일종으로 작동합니다. 예를 들어 탭 컨트롤을 추가 탭 보기로 스크롤할 수 있도록 스핀 단추 컨트롤을 경우에 따라 표시 합니다.

사용 하 여 대 한 자세한 내용은 `CSpinButtonCtrl`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 하 고 [CSpinButtonCtrl 사용 하 여](../../mfc/using-cspinbuttonctrl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="create"></a>  CSpinButtonCtrl::Create

스핀 단추 컨트롤을 만들고 연결 하는 `CSpinButtonCtrl` 개체...

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
스핀 단추 컨트롤의 스타일을 지정합니다. 스핀 단추 컨트롤 스타일의 조합을 컨트롤에 적용 됩니다. 이러한 스타일에 설명 되어 있습니다 [Up-down 컨트롤 스타일](/windows/desktop/Controls/up-down-control-styles) Windows SDK에 있습니다.

*rect*<br/>
스핀 단추 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조

*pParentWnd*<br/>
스핀 단추 컨트롤의 부모 창에 일반적으로 포인터를 `CDialog`입니다. NULL이 아니어야 합니다.

*nID*<br/>
스핀 단추 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성을 `CSpinButtonCtrl` 처음 두 단계에서 개체 생성자를 호출 하 고, 호출 하 `Create`, spin button 컨트롤을 만들고에 연결 하는 `CSpinButtonCtrl` 개체입니다.

확장된 창 스타일을 사용 하 여 스핀 단추 컨트롤을 만들려면, 호출 [CSpinButtonCtrl::CreateEx](#createex) 대신 `Create`합니다.

##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 된 `CSpinButtonCtrl` 개체입니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
만들려는 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조를 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK의 합니다.

*dwStyle*<br/>
스핀 단추 컨트롤의 스타일을 지정합니다. 스핀 단추 컨트롤 스타일의 조합을 컨트롤에 적용 됩니다. 이러한 스타일에 설명 되어 있습니다 [Up-down 컨트롤 스타일](/windows/desktop/Controls/up-down-control-styles) Windows SDK에 있습니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 크기와의 클라이언트 좌표에서 만든 창의 위치를 설명 하는 구조 *pParentWnd*합니다.

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 `CreateEx` of [만들기](#create) WS_EX_ Windows 확장된 스타일 앞으로 지정 된 Windows 확장된 스타일을 적용 합니다.

##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl

`CSpinButtonCtrl` 개체를 생성합니다.

```
CSpinButtonCtrl();
```

##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel

스핀 단추 컨트롤에 대 한 가속 정보를 검색합니다.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>매개 변수

*nAccel*<br/>
지정 된 배열의 요소 수가 *pAccel*합니다.

*pAccel*<br/>
배열에 대 한 포인터 [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) 가속 정보를 수신 하는 구조입니다.

### <a name="return-value"></a>반환 값

검색 수 가속기 구조입니다.

##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase

스핀 단추 컨트롤에 대 한 현재 자료를 검색합니다.

```
UINT GetBase() const;
```

### <a name="return-value"></a>반환 값

현재 기본 값입니다.

##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy

현재 버디 창에 대 한 포인터를 검색합니다.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>반환 값

현재 버디 창에 대 한 포인터입니다.

##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos

스핀 단추 컨트롤의 현재 위치를 검색합니다.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpbError*<br/>
값 0으로 설정 하는 부울 값에 대 한 포인터는 성공적으로 검색 하거나 오류가 발생 한 경우 0이 아닌 경우 이 매개 변수는 NULL로 설정 하는 경우 오류가 보고 되지 않습니다.

### <a name="return-value"></a>반환 값

첫 번째 버전 하위 단어에서 16 비트 현재 위치를 반환 합니다. 상위 단어는 오류가 발생 한 경우 0이 아닌 값입니다.

두 번째 버전은 32 비트 위치를 반환합니다.

### <a name="remarks"></a>설명

반환 되는 값을 처리할 때 컨트롤 버디 창 캡션에 따라 현재 위치를 업데이트 합니다. 컨트롤 버디 창 없는 경우 또는 캡션을 잘못 되었거나 범위를 벗어난 값을 지정 하는 경우에 오류가 발생 합니다.

##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange

스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 검색합니다.

```
DWORD GetRange() const;

void GetRange(
    int& lower,
    int& upper) const;

void GetRange32(
    int& lower,
    int &upper) const;
```

### <a name="parameters"></a>매개 변수

*lower*<br/>
컨트롤에 대 한 하한값을 수신 하는 정수에 대 한 참조입니다.

*upper*<br/>
컨트롤에 대 한 상한값을 수신 하는 정수에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

첫 번째 버전 최대값과 최소값을 포함 하는 32 비트 값을 반환 합니다. 하위 워드 컨트롤에 대 한 상한값 이며 상위 word 하한값입니다.

### <a name="remarks"></a>설명

멤버 함수 `GetRange32` 32 비트 정수로 스핀 단추 컨트롤의 범위를 검색 합니다.

##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel

스핀 단추 컨트롤에 대 한 가속을 설정합니다.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>매개 변수

*nAccel*<br/>
수가 [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) 에서 지정한 구조의 *pAccel*합니다.

*pAccel*<br/>
가속 정보가 포함 된 UDACCEL 구조의 배열에 대 한 포인터입니다. 요소에 따라 오름차순으로 정렬할지를 `nSec` 멤버입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase

스핀 단추 컨트롤을 설정 합니다.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>매개 변수

*nBase*<br/>
컨트롤에 대 한 새 기본 값입니다. 10 진수에 대 한 10 또는 16 진수 수 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 이전 기본 값 이거나 잘못 된 자료를 지정 하는 경우 0입니다.

### <a name="remarks"></a>설명

기본 값 10 진수 또는 16 자리 숫자 버디 창에 표시 되는지 여부를 결정 합니다. 16 진수 숫자는 항상 부호가; 10 진수 서명 됩니다.

##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy

스핀 단추 컨트롤의 버디 창을 설정입니다.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>매개 변수

*pWndBuddy*<br/>
새 버디 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

이전 버디 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

Spin 컨트롤의 편집 컨트롤을 일부 콘텐츠를 표시 하는 등의 다른 창과 사용 하 여 거의 항상 관련이 있습니다. 이 다른 창은 spin 컨트롤의 "동반" 라고 합니다.

##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos

스핀 단추 컨트롤에 대 한 현재 위치를 설정합니다.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
컨트롤에 대 한 새 위치입니다. 이 값을 컨트롤에 대 한 상한 및 하 한 제한으로 지정 된 범위에 있어야 합니다.

### <a name="return-value"></a>반환 값

이전 위치 (16 비트 전체 자릿수 `SetPos`32 비트에 대 한 전체 자릿수 `SetPos32`).

### <a name="remarks"></a>설명

`SetPos32` 32 비트 위치를 설정 합니다.

##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange

스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 설정합니다.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>매개 변수

*nLower* 고 *nUpper*<br/>
컨트롤에 대 한 상한 및 하 한 제한입니다. 에 대 한 `SetRange`, 모두 제한 UD_MAXVAL 보다 클 수 또는 UD_MINVAL; 미만 또한의 차이 두 가지 제한 초과할 수 없습니다 UD_MAXVAL 합니다. `SetRange32` 제한;에 제한을 두지합니다 모든 정수를 사용 합니다.

### <a name="remarks"></a>설명

멤버 함수 `SetRange32` spin button 컨트롤에 대 한 32 비트 범위를 설정 합니다.

> [!NOTE]
>  스핀 단추에 대 한 기본 범위에 영 (0)으로 설정 된 최대값 및 최소값 100으로 있습니다. 최 댓 값이 최소값 보다 작은 이기 때문에 위치 줄어듭니다 위쪽 화살표를 클릭 하 고 아래쪽 화살표를 클릭 하 고 증가 합니다. 사용 하 여 `CSpinButtonCtrl::SetRange` 이러한 값을 조정 합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CSliderCtrl 클래스](../../mfc/reference/csliderctrl-class.md)
