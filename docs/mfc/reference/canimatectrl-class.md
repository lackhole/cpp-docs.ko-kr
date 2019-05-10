---
title: CAnimateCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
ms.openlocfilehash: 867bec619dc633b7b1fbf9785e14132ba8c493ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151294"
---
# <a name="canimatectrl-class"></a>CAnimateCtrl 클래스

Windows 공용 애니메이션 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CAnimateCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|`CAnimateCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAnimateCtrl::Close](#close)|AVI 클립을 닫습니다.|
|[CAnimateCtrl::Create](#create)|애니메이션 컨트롤을 만들고 연결 하는 `CAnimateCtrl` 개체입니다.|
|[CAnimateCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 애니메이션 컨트롤을 만들고 연결 하는 `CAnimateCtrl` 개체입니다.|
|[CAnimateCtrl::IsPlaying](#isplaying)|오디오-비디오 인터리빙 (AVI) 클립에서 재생 여부를 나타냅니다.|
|[CAnimateCtrl::Open](#open)|파일 또는 리소스에서 AVI 클립을 열고 첫 번째 프레임을 표시 합니다.|
|[CAnimateCtrl::Play](#play)|사운드 없이 AVI 클립을 재생합니다.|
|[CAnimateCtrl::Seek](#seek)|AVI 클립의 선택한 단일 프레임을 표시합니다.|
|[CAnimateCtrl::Stop](#stop)|AVI 클립의 재생을 중지 합니다.|

## <a name="remarks"></a>설명

이 컨트롤 (및 따라서는 `CAnimateCtrl` 클래스) 이상 Windows 95, Windows 98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.

애니메이션 컨트롤은 클립 AVI (오디오 비디오 인터리빙) 형식으로 표시 되는 사각형 창을-표준 Windows 비디오/오디오 형식입니다. AVI 클립은 일련의 동영상 같은 비트맵 프레임입니다.

애니메이션 컨트롤 간단한 AVI 클립을 재생할 수 있습니다. 특히 애니메이션 컨트롤에서 재생할 수 클립에는 다음 요구 사항을 충족 해야 합니다.

- 정확히 하나의 비디오 스트림 이어야 하 고 프레임 하나 이상 있어야 합니다.

- 에 있을 수 있습니다 최대 두 스트림을 파일 (일반적으로 다른 스트림에 있는 경우는 오디오 스트림, 애니메이션 컨트롤은 오디오 정보를 무시 하지만).

- 클립 압축 되지 않은 또는 RLE8 압축으로 압축 해야 합니다.

- 팔레트 변경 하지 않고 비디오 스트림의 수입니다.

AVI 클립 AVI 리소스로 응용 프로그램에 추가 하거나 응용 프로그램으로 별도 AVI 파일와 함께 보낼 수 있습니다.

스레드가 계속 AVI 클립 표시 되는 동안 실행을 애니메이션 컨트롤의 일반적 용도 중 하나 이므로 시간이 오래 걸리는 작업 중 시스템 작업을 나타냅니다. 예를 들어, 파일 탐색기의 찾기 대화 상자에서 파일 시스템 검색으로 이동 돋보기 효과 표시합니다.

만드는 경우는 `CAnimateCtrl` 상자 또는 대화 상자 편집기를 사용 하 여 대화 상자 리소스에서 자동으로 소멸 됩니다 사용자 대화 상자를 닫을 때 대화 상자 내에서 개체입니다.

만드는 경우는 `CAnimateCtrl` 창 내에서 개체 삭제 해야 할 수 있습니다. 만드는 경우는 `CAnimateCtrl` 개체 스택에 자동으로 제거 됩니다. 만드는 경우는 `CAnimateCtrl` 를 사용 하 여 힙에 있는 개체에는 **새** 를 호출 해야 함수 **삭제** 개체 삭제에 대. 새 클래스를 파생 하는 경우 `CAnimateCtrl` 해당 클래스의 메모리를 할당 하 고, 재정의 `CAnimateCtrl` 소멸자는 할당을 삭제 합니다.

사용 하 여 대 한 자세한 내용은 `CAnimateCtrl`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 하 고 [CAnimateCtrl 사용 하 여](../../mfc/using-canimatectrl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="canimatectrl"></a>  CAnimateCtrl::CAnimateCtrl

`CAnimateCtrl` 개체를 생성합니다.

```
CAnimateCtrl();
```

### <a name="remarks"></a>설명

호출 해야 합니다 [만들기](#create) 만든 개체에서 다른 작업을 수행 하기 전에 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

##  <a name="close"></a>  CAnimateCtrl::Close

메모리에서 제거 합니다 (있는 경우) 애니메이션 컨트롤에서 이전에 연 AVI 클립을 닫습니다.

```
BOOL Close();
```

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.

##  <a name="create"></a>  CAnimateCtrl::Create

애니메이션 컨트롤을 만들고 연결 하는 `CAnimateCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
애니메이션 컨트롤의 스타일을 지정합니다. 아래의 설명 섹션 및 애니메이션 컨트롤 스타일에 설명 하는 스타일에 설명 된 windows 어떤 조합도 적용할 [애니메이션 컨트롤 스타일](/windows/desktop/Controls/animation-control-styles) Windows SDK에 있습니다.

*rect*<br/>
애니메이션 컨트롤의 위치와 크기를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조입니다.

*pParentWnd*<br/>
애니메이션 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. NULL이 아니어야 합니다.

*nID*<br/>
애니메이션 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CAnimateCtrl` 두 단계에서. 먼저 생성자를 호출 하 고 호출 `Create`, 애니메이션 컨트롤을 만들고 연결 하는 `CAnimateCtrl` 개체입니다.

다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 애니메이션 컨트롤입니다.

- WS_CHILD 항상

- WS_VISIBLE 일반적으로

- WS_DISABLED 거의

애니메이션 컨트롤을 사용 하 여 확장된 창 스타일을 사용 하려는 경우 호출할 [CreateEx](#createex) 대신 `Create`합니다.

위에 나열 된 창 스타일, 외에도 애니메이션 컨트롤에 하나 이상의 애니메이션 컨트롤 스타일을 적용 하는 것이 좋습니다. 자세한 내용은 Windows SDK에서 참조 [애니메이션 컨트롤 스타일](/windows/desktop/Controls/animation-control-styles)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.

##  <a name="createex"></a>  CAnimateCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 된 `CAnimateCtrl` 개체입니다.

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
애니메이션 컨트롤의 스타일을 지정합니다. 에 설명 된 애니메이션 컨트롤 스타일 및 창의 어떤 조합도 적용할 [애니메이션 컨트롤 스타일](/windows/desktop/Controls/animation-control-styles) Windows SDK에 있습니다.

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

##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying

오디오-비디오 인터리빙 (AVI) 클립에서 재생 여부를 나타냅니다.

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 AVI 클립에서 재생 됩니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [ACM_ISPLAYING](/windows/desktop/Controls/acm-isplaying) Windows SDK에 설명 된 메시지입니다.

##  <a name="open"></a>  CAnimateCtrl::Open

AVI 클립을 열고 해당 첫 번째 프레임을 표시 하려면이 함수를 호출 합니다.

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
`CString` 개체나 AVI 파일의 이름 또는 AVI 리소스의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수가 NULL 인 경우 시스템 있으면 애니메이션 컨트롤에 대해 이전에 연 AVI 클립을 닫습니다.

*nID*<br/>
AVI 리소스 식별자입니다. 이 매개 변수가 NULL 인 경우 시스템 있으면 애니메이션 컨트롤에 대해 이전에 연 AVI 클립을 닫습니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

AVI 리소스 애니메이션 컨트롤을 만든 모듈에서 로드 됩니다.

`Open` AVI 클립;에서 소리를 지원 하지 않습니다. 자동 AVI 클립을 열 수 있습니다.

애니메이션 컨트롤에 있으면는 `ACS_AUTOPLAY` 스타일 애니메이션 컨트롤 자동으로 시작 되며 열리는 직후 클립을 재생 합니다. 스레드가 계속 실행 하는 동안 백그라운드에서 클립을 재생을 계속 됩니다. 클립 완료 되 면 재생 하 고 자동으로 반복 됩니다.

애니메이션 컨트롤에 있으면는 `ACS_CENTER` 스타일 AVI 클립은 컨트롤의 가운데에 맞춰지고 컨트롤의 크기가 변경 되지 것입니다. 애니메이션 컨트롤에 없는 경우는 `ACS_CENTER` 스타일, 컨트롤은 AVI 클립 AVI 클립의 이미지의 크기에 열려 있을 때 크기가 조정 됩니다. 컨트롤의 왼쪽된 위 모퉁이의 위치 변경 되지 않습니다, 컨트롤의 크기.

애니메이션 컨트롤에 있으면는 `ACS_TRANSPARENT` 스타일 투명 한 배경을 사용 하 여 첫 번째 프레임을 그릴지에 배경색을 지정 하지 않고 애니메이션 클립 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.

##  <a name="play"></a>  CAnimateCtrl::Play

애니메이션 컨트롤에서 AVI 클립을 재생 하려면이 함수를 호출 합니다.

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>매개 변수

*nFrom*<br/>
재생 시작 되는 프레임의 인덱스 0부터 시작 합니다. 값 보다 작거나 65,536 여야 합니다. 값이 0 AVI 클립의 첫 번째 프레임을 시작으로 의미 합니다.

*nTo*<br/>
프레임의 0부터 시작 인덱스는 종료를 재생 합니다. 값 보다 작거나 65,536 여야 합니다. 값이-1 이면 AVI 클립에서 마지막 프레임을 사용 하 여 종료 합니다.

*nRep*<br/>
AVI 클립 재생 횟수입니다. 값-1 파일을 무기한 재생 의미 합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

애니메이션 컨트롤 스레드가 계속 실행 하는 동안 백그라운드에서 클립을 재생 됩니다. 애니메이션 컨트롤에 있으면 `ACS_TRANSPARENT` 스타일 AVI 클립 재생 될 애니메이션 클립에 지정 된 배경색 보다는 투명 한 배경을 사용 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.

##  <a name="seek"></a>  CAnimateCtrl::Seek

정적으로 AVI 클립의 단일 프레임을 표시 하려면이 함수를 호출 합니다.

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>매개 변수

*nTo*<br/>
표시할 프레임의 인덱스 0부터 시작 합니다. 값 보다 작거나 65,536 여야 합니다. 값이 0 AVI 클립의 첫 번째 프레임을 표시 하는 것을 의미 합니다. 값이-1 의미 AVI 클립에서 마지막 프레임을 표시 합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

애니메이션 컨트롤에 있으면 `ACS_TRANSPARENT` 스타일 투명 한 배경을 사용 하 여 AVI 클립을 그릴에 배경색을 지정 하지 않고 애니메이션 클립 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.

##  <a name="stop"></a>  CAnimateCtrl::Stop

애니메이션 컨트롤에서 AVI 클립을 재생을 중지 하려면이 함수를 호출 합니다.

```
BOOL Stop();
```

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl::Create](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)
