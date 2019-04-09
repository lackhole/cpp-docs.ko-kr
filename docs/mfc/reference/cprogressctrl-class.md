---
title: CProgressCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
ms.openlocfilehash: 15241485278f09d16c86fc7274f2fc1d85a7a2f7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778951"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl 클래스

Windows의 공용 진행률 표시줄 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|`CProgressCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CProgressCtrl::Create](#create)|진행률 표시줄 컨트롤을 만들고 연결 하는 `CProgressCtrl` 개체입니다.|
|[CProgressCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 진행률 컨트롤을 만들고 연결 하는 `CProgressCtrl` 개체입니다.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|현재 진행률 표시줄 컨트롤에 대 한 진행률 표시줄의 색을 가져옵니다.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|현재 진행률 표시줄의 배경색을 가져옵니다.|
|[CProgressCtrl::GetPos](#getpos)|진행률 표시줄의 현재 위치를 가져옵니다.|
|[CProgressCtrl::GetRange](#getrange)|진행률 표시줄 컨트롤의 범위는 한 및 상한 제한을 가져옵니다.|
|[CProgressCtrl::GetState](#getstate)|현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.|
|[CProgressCtrl::GetStep](#getstep)|현재 진행률 표시줄 컨트롤의 진행률 표시줄에 대 한 단계 증가 검색합니다.|
|[CProgressCtrl::OffsetPos](#offsetpos)|지정 된 증분만큼 진행률 표시줄 컨트롤의 현재 위치를 이동 하 고 새 위치를 반영 하도록 막대를 다시 그립니다.|
|[CProgressCtrl::SetBarColor](#setbarcolor)|현재 진행률 표시줄 컨트롤에는 진행률 표시기의 색을 설정합니다.|
|[CProgressCtrl::SetBkColor](#setbkcolor)|진행률 표시줄의 배경색을 설정합니다.|
|[CProgressCtrl::SetMarquee](#setmarquee)|움직이는 텍스트 모드를 켜거나 현재 진행률 표시줄 컨트롤을 설정합니다.|
|[CProgressCtrl::SetPos](#setpos)|진행률 표시줄 컨트롤에 대 한 현재 위치를 설정 하 고 새 위치를 반영 하도록 막대를 다시 그립니다.|
|[CProgressCtrl::SetRange](#setrange)|진행률 표시줄 컨트롤에 대 한 최소 및 최대 범위를 설정 하 고 새 범위를 반영 하도록 모음을 다시 그립니다.|
|[CProgressCtrl::SetState](#setstate)|현재 진행률 표시줄 컨트롤의 상태를 설정합니다.|
|[CProgressCtrl::SetStep](#setstep)|진행률 표시줄 컨트롤에 대 한 단계 증분 값을 지정 합니다.|
|[CProgressCtrl::StepIt](#stepit)|진행률 표시줄 컨트롤에 대 한 현재 위치를 앞으로 이동 단계 증분만큼 (참조 [SetStep](#setstep)) 하 고 새 위치를 반영 하도록 모음을 다시 그립니다.|

## <a name="remarks"></a>설명

진행률 표시줄 컨트롤에는 응용 프로그램 시간이 오래 걸리는 작업의 진행률을 표시 하는 데 사용할 수 있는 창입니다. 왼쪽에서 오른쪽 시스템과 강조 색을 작업이 진행 됨에 따라 점진적으로 채워진 사각형 이루어져 있습니다.

진행률 표시줄 컨트롤을 범위 및 현재 위치에 있습니다. 범위 작업의 총 기간을 나타내고, 현재 위치 작업 완료에 대 한 응용 프로그램에 대 한 진행률을 나타냅니다. 창 프로시저의 강조 색을 채울 진행률 표시줄의 비율을 결정 하는 범위 및 현재 위치를 사용 합니다. 범위 및 현재 위치 값을 부호 있는 정수로 표현 되는 때문에 가능한 현재 위치 값의 범위가-2,147,483,648에서 2,147,483,647까지 포괄 합니다.

사용 하 여 대 한 자세한 내용은 `CProgressCtrl`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 하 고 [CProgressCtrl 사용 하 여](../../mfc/using-cprogressctrl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl

`CProgressCtrl` 개체를 생성합니다.

```
CProgressCtrl();
```

### <a name="remarks"></a>설명

생성 한 후는 `CProgressCtrl` 개체를 호출 `CProgressCtrl::Create` 진행률 표시줄 컨트롤을 만들려고 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

##  <a name="create"></a>  CProgressCtrl::Create

진행률 표시줄 컨트롤을 만들고 연결 하는 `CProgressCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
진행률 표시줄 컨트롤의 스타일을 지정합니다. 창 stylesdescribed 어떤 조합도 적용할 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) 다음 진행률 표시줄 컨트롤 스타일, 컨트롤 외에도 Windows sdk에서:

- PBS_VERTICAL 표시 정보를 세로 방향으로 진행으로 위쪽에서 아래쪽입니다. 이 플래그가 없으면 진행률 표시줄 컨트롤에서 오른쪽으로 수평, 왼쪽 표시합니다.

- 진행률 표시줄 컨트롤에서 데이터를 입력할 부드러운 PBS_SMOOTH 표시 점진적입니다. 이 플래그가 없으면 블록을 사용 하 여 컨트롤을 채웁니다.

*rect*<br/>
진행률 표시줄 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조입니다. 클라이언트 영역을 기준으로 지정 된 좌표는 컨트롤을 자식 창와 있어야 하므로 합니다 *pParentWnd*합니다.

*pParentWnd*<br/>
일반적으로 진행률 표시줄 컨트롤의 부모 창 지정을 `CDialog`입니다. NULL이 아니어야 합니다.

*nID*<br/>
진행률 표시줄 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

True는 `CProgressCtrl` 개체를 만들었습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

생성 된 `CProgressCtrl` 두 단계에서 개체입니다. 먼저, 만드는 생성자를 호출 합니다 `CProgressCtrl` 개체를 호출 `Create`는 진행률 표시줄 컨트롤을 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

##  <a name="createex"></a>  CProgressCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 된 `CProgressCtrl` 개체입니다.

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
만들려는 컨트롤의 확장된 스타일을 지정 합니다. 확장 된 Windows 스타일의 목록은 참조 하세요. 합니다 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK의 합니다.

*dwStyle*<br/>
진행률 표시줄 컨트롤의 스타일을 지정합니다. 에 설명 된 창 스타일의 조합을 적용 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK에 있습니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 크기와의 클라이언트 좌표에서 만든 창의 위치를 설명 하는 구조 *pParentWnd*합니다.

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 `CreateEx` of [Create](#create) Windows 확장된 스타일 앞으로 지정 된 Windows 확장된 스타일을 적용할 **WS_EX_** 합니다.

##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor

현재 진행률 표시줄 컨트롤에 대 한 진행률 표시줄의 색을 가져옵니다.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>반환 값

현재 진행률 표시줄의 색으로 표시 된 [COLORREF](/windows/desktop/gdi/colorref) 값 또는 CLR_DEFAULT 진행률 표시기 막대의 색은 기본 색 하는 경우.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PBM_GETBARCOLOR](/windows/desktop/Controls/pbm-getbarcolor) Windows SDK에 설명 된 메시지입니다.

##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor

현재 진행률 표시줄의 배경색을 가져옵니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>반환 값

현재 진행률 표시줄의 배경색으로 표시 된 [COLORREF](/windows/desktop/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PBM_GETBKCOLOR](/windows/desktop/Controls/pbm-getbkcolor) Windows SDK에 설명 된 메시지입니다.

##  <a name="getpos"></a>  CProgressCtrl::GetPos

진행률 표시줄의 현재 위치를 검색합니다.

```
int GetPos();
```

### <a name="return-value"></a>반환 값

진행률 표시줄 컨트롤의 위치입니다.

### <a name="remarks"></a>설명

진행률 표시줄 컨트롤의 위치, 화면의 실제 위치가 아닙니다. 하지만 대신 위에서 하위 범위에 표시 됩니다 [SetRange](#setrange)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

##  <a name="getrange"></a>  CProgressCtrl::GetRange

현재 한 및 상한 제한 또는 진행률 표시줄 컨트롤의 범위를 가져옵니다.

```
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>매개 변수

*nLower*<br/>
진행률 표시줄 컨트롤의 하한값을 수신 하는 정수에 대 한 참조입니다.

*nUpper*<br/>
진행률 표시줄 컨트롤의 상한값을 수신 하는 정수에 대 한 참조입니다.

### <a name="remarks"></a>설명

이 함수에서 참조 하는 정수 한 및 상한 제한 값을 복사 *nLower* 하 고 *nUpper*, 각각.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

##  <a name="getstate"></a>  CProgressCtrl::GetState

현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.

```
int GetState() const;
```

### <a name="return-value"></a>반환 값

다음 값 중 하나는 현재 진행률 표시줄 컨트롤의 상태:

|값|상태|
|-----------|-----------|
|PBST_NORMAL|진행 중|
|PBST_ERROR|Error|
|PBST_PAUSED|일시 중지됨|

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PBM_GETSTATE](/windows/desktop/Controls/pbm-getstate) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 상태를 검색합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

##  <a name="getstep"></a>  CProgressCtrl::GetStep

현재 진행률 표시줄 컨트롤의 진행률 표시줄에 대 한 단계 증가 검색합니다.

```
int GetStep() const;
```

### <a name="return-value"></a>반환 값

진행률 표시줄의 단계 증가값입니다.

### <a name="remarks"></a>설명

단계 증가값이 크기에 대 한 호출 [CProgressCtrl::StepIt](#stepit) 진행률 표시줄의 현재 위치를 증가 합니다.

이 메서드는 전송 된 [PBM_GETSTEP](/windows/desktop/Controls/pbm-getstep) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 단계 증가 검색합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos

진행률 표시줄 컨트롤의 현재 위치를 앞으로 이동 하 여 지정 된 증분만큼 *nPos* 새 위치를 반영 하도록 막대를 다시 그립니다.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
위치로 이동 하 여 크기입니다.

### <a name="return-value"></a>반환 값

진행률 표시줄 컨트롤의 이전 위치입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor

현재 진행률 표시줄 컨트롤에는 진행률 표시기의 색을 설정합니다.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*clrBar*|[in] A [COLORREF](/windows/desktop/gdi/colorref) 새로운 진행률 표시줄의 색을 지정 하는 값입니다. 기본 색을 사용 하 여 진행률 표시줄이 시킬 CLR_DEFAULT를 지정 합니다.|

### <a name="return-value"></a>반환 값

진행률 표시줄의 이전 색으로 표시를 [COLORREF](/windows/desktop/gdi/colorref) 값 또는 CLR_DEFAULT 경우 진행률 표시줄의 색은 기본 색입니다.

### <a name="remarks"></a>설명

합니다 `SetBarColor` 메서드는 Windows Vista 진행률 표시줄 경우에만 색을 설정 [테마](/windows/desktop/Controls/visual-styles-overview) 은 적용 되지 않습니다.

이 메서드는 전송 된 [PBM_SETBARCOLOR](/windows/desktop/Controls/pbm-setbarcolor) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 빨간색, 녹색, 파랑 또는 기본값에 진행률 표시줄의 색을 변경합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor

진행률 표시줄의 배경색을 설정합니다.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>매개 변수

*clrNew*<br/>
새 배경 색을 지정 하는 COLORREF 값입니다. 진행률 표시줄에 대 한 기본 배경색을 사용 하 여 CLR_DEFAULT 값을 지정 합니다.

### <a name="return-value"></a>반환 값

합니다 [COLORREF](/windows/desktop/gdi/colorref) 배경색은 기본 색 경우 이전 배경 색 또는 CLR_DEFAULT를 나타내는 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee

움직이는 텍스트 모드를 켜거나 현재 진행률 표시줄 컨트롤을 설정합니다.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*fMarqueeMode*|[in] 설정 움직이는 텍스트 모드를 켜 짐 또는 움직이는 텍스트 모드를 해제 하려면 FALSE true로 설정 하면입니다.|
|*nInterval*|[in] 움직이는 텍스트 애니메이션의 업데이트 간격 (밀리초) 시간입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

움직이는 텍스트 모드가 켜져 진행률 표시줄은 애니메이션이 적용 하 고 스크롤합니다 같은 극장식 움직이는 텍스트 로그온입니다.

이 메서드는 전송 된 [PBM_SETMARQUEE](/windows/desktop/Controls/pbm-setmarquee) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제는 시작 하 고 움직이는 애니메이션을 중지 합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

##  <a name="setpos"></a>  CProgressCtrl::SetPos

진행률 표시줄 컨트롤의 현재 위치에 지정 된 대로 설정 *nPos* 새 위치를 반영 하도록 막대를 다시 그립니다.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
진행률 표시줄 컨트롤의 새 위치입니다.

### <a name="return-value"></a>반환 값

진행률 표시줄 컨트롤의 이전 위치입니다.

### <a name="remarks"></a>설명

진행률 표시줄 컨트롤의 위치, 화면의 실제 위치가 아닙니다. 하지만 대신 위에서 하위 범위에 표시 됩니다 [SetRange](#setrange)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

##  <a name="setrange"></a>  CProgressCtrl::SetRange

진행률 표시줄 컨트롤의 범위 상한 및 하 한 크기 제한을 설정 하 고 새 범위를 반영 하기 위해 막대를 다시 그립니다.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>매개 변수

*nLower*<br/>
범위의 하한값을 지정 합니다 (기본값은 0).

*nUpper*<br/>
범위의 상한을 지정 (기본값: 100).

### <a name="remarks"></a>설명

멤버 함수 `SetRange32` 진행률 컨트롤에 대 한 32 비트 범위를 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

##  <a name="setstate"></a>  CProgressCtrl::SetState

현재 진행률 표시줄 컨트롤의 상태를 설정합니다.

```
int SetState(int iState);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iState*|[in] 상태 진행률 표시줄 설정입니다. 다음 값 중 하나를 사용합니다.<br /><br /> -PBST_NORMAL-진행 중<br />-PBST_ERROR-오류<br />-PBST_PAUSED-일시 중지|

### <a name="return-value"></a>반환 값

현재 진행률 표시줄 컨트롤의 이전 상태입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PBM_SETSTATE](/windows/desktop/Controls/pbm-setstate) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 상태를 일시 중지됨 또는 진행 중으로 설정합니다.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

##  <a name="setstep"></a>  CProgressCtrl::SetStep

진행률 표시줄 컨트롤에 대 한 단계 증분 값을 지정 합니다.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>매개 변수

*nStep*<br/>
새 단계 증가값입니다.

### <a name="return-value"></a>반환 값

이전 단계 증가값입니다.

### <a name="remarks"></a>설명

단계 증가 되는에 대 한 호출 `CProgressCtrl::StepIt` 증가 진행률 표시줄의 현재 위치입니다.

기본 단계 증가분은 10입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

##  <a name="stepit"></a>  CProgressCtrl::StepIt

단계 증분만큼 진행률 표시줄 컨트롤에 대 한 현재 위치를 이동 하 고 새 위치를 반영 하도록 막대를 다시 그립니다.

```
int StepIt();
```

### <a name="return-value"></a>반환 값

진행률 표시줄 컨트롤의 이전 위치입니다.

### <a name="remarks"></a>설명

단계 증가값으로 설정 됩니다는 `CProgressCtrl::SetStep` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
