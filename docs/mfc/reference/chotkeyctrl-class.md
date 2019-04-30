---
title: CHotKeyCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
ms.openlocfilehash: 66edc7d4a1b4c78480da7d11cf30f7feeecefe2c
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339550"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl 클래스

Windows의 공용 바로 가기 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHotKeyCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|`CHotKeyCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CHotKeyCtrl::Create](#create)|바로 가기 키 컨트롤을 만들고 연결 하는 `CHotKeyCtrl` 개체입니다.|
|[CHotKeyCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 바로 가기 키 컨트롤을 만들고 연결 하는 `CHotKeyCtrl` 개체입니다.|
|[CHotKeyCtrl::GetHotKey](#gethotkey)|바로 가기 키 컨트롤에서 가상 키 코드 및 한정자 플래그의 바로 가기 키를 검색합니다.|
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|바로 가기 키에 할당 된 로컬 문자 집합에서 키 이름을 검색 합니다.|
|[CHotKeyCtrl::GetKeyName](#getkeyname)|지정된 된 가상 키 코드에 할당 된 로컬 문자 집합에서 키 이름을 검색 합니다.|
|[CHotKeyCtrl::SetHotKey](#sethotkey)|바로 가기 키 컨트롤에 대 한 바로 가기 키 조합을 설정합니다.|
|[CHotKeyCtrl::SetRules](#setrules)|잘못 된 조합이 및 바로 가기 키 컨트롤에 대 한 기본 한정자 조합을 정의합니다.|

## <a name="remarks"></a>설명

"바로 가기 키 컨트롤"에 바로 가기 키를 만들 수 있도록 하는 창입니다. "바로 가기 키"는 작업을 신속 하 게 수행 하려면 사용자를 누를 수는 키 조합입니다. (예를 들어 사용자 만들면 지정된 된 창 활성화 및 Z 순서의 맨 위에 제공 하는 바로 가기 키를.) Hot key 컨트롤 사용자의 선택 항목을 표시 하 고 사용자가 올바른 키조합을 확인 합니다.

이 컨트롤 (및 따라서는 `CHotKeyCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.

사용자가 키 조합의 선택한 경우 응용 프로그램 컨트롤에서 지정 된 키 조합을 검색 하 고 WM_SETHOTKEY 메시지를 사용 하 여 시스템에 바로 가기 키를 설정할 수 있습니다. 사용자를 누를 때마다 바로 가기 키 이후부터 시스템의 모든 부분에서 WM_SETHOTKEY 메시지에 지정 된 창의 SC_HOTKEY 지정 WM_SYSCOMMAND 메시지를 받습니다. 이 메시지에 수신 하는 창을 활성화 합니다. 바로 가기 키까지 WM_SETHOTKEY 종료를 호출 하는 응용 프로그램의 경우 유효 합니다.

이 메커니즘은 WM_HOTKEY 메시지는 Windows에 따라 달라 지는 바로 가기 키 지원 다릅니다 [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey) 하 고 [UnregisterHotKey](/windows/desktop/api/winuser/nf-winuser-unregisterhotkey) 함수입니다.

사용 하 여 대 한 자세한 내용은 `CHotKeyCtrl`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 하 고 [CHotKeyCtrl 사용 하 여](../../mfc/using-chotkeyctrl.md).

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl

`CHotKeyCtrl` 개체를 생성합니다.

```
CHotKeyCtrl();
```

##  <a name="create"></a>  CHotKeyCtrl::Create

바로 가기 키 컨트롤을 만들고 연결 하는 `CHotKeyCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
바로 가기 키 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용 됩니다. 참조 [공용 컨트롤 스타일](/windows/desktop/Controls/common-control-styles) 자세한 내용은 Windows sdk입니다.

*rect*<br/>
바로 가기 키 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT 구조체](/windows/desktop/api/windef/ns-windef-tagrect)합니다.

*pParentWnd*<br/>
바로 가기 키 컨트롤의 부모 창에 일반적으로 지정 된 [CDialog](../../mfc/reference/cdialog-class.md)합니다. NULL이 아니어야 합니다.

*nID*<br/>
바로 가기 키 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

0이 아닌 경우 초기화에 성공 하면 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CHotKeyCtrl` 두 단계에서 개체입니다. 먼저 생성자를 호출 하 고 호출 `Create`, hot key 컨트롤을 만들고 연결 하는 `CHotKeyCtrl` 개체입니다.

컨트롤을 사용 하 여 확장된 창 스타일을 사용 하려는 경우 호출할 [CreateEx](#createex) 대신 `Create`합니다.

##  <a name="createex"></a>  CHotKeyCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 하려면이 함수를 호출 합니다 `CHotKeyCtrl` 개체입니다.

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
바로 가기 키 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용 됩니다. 자세한 내용은 [공용 컨트롤 스타일](/windows/desktop/Controls/common-control-styles) Windows SDK의 합니다.

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

##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey

바로 가기 키 컨트롤에서 가상 키 코드 및 한정자 플래그의 바로 가기 키를 검색합니다.

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>매개 변수

*wVirtualKeyCode*<br/>
[out] 바로 가기 키의 가상 키 코드입니다. 에서 표준 가상 키 코드 목록은 Winuser.h를 참조 하세요.

*wModifiers*<br/>
[out] 바로 가기 키의 한정자 키를 나타내는 플래그의 비트 조합 (OR)입니다.

보조키 플래그는 다음과 같습니다.

|플래그|해당 키|
|----------|-----------------------|
|HOTKEYF_ALT|Alt 키|
|HOTKEYF_CONTROL|CTRL 키|
|HOTKEYF_EXT|확장 된 키|
|HOTKEYF_SHIFT|Shift 키|

### <a name="return-value"></a>반환 값

첫 번째에서 오버 로드 된 메서드를 가상 키 코드 및 한정자 플래그를 포함 하는 DWORD입니다. 가상 키 코드를 포함 하는 하위 단어의 낮은 순서 바이트, 보조키 플래그를 포함 하는 하위 단어의 높은 순서 바이트가 및 상위 word가 0입니다.

### <a name="remarks"></a>설명

가상 키 코드와 함께 보조키 바로 가기 키를 정의합니다.

##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName

바로 가기 키의 지역화 된 이름을 가져오려면이 함수를 호출 합니다.

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>반환 값

현재 선택한 바로 가기 키의 지역화 된 이름입니다. 선택한 바로 가기 키 이면 `GetHotKeyName` 빈 문자열을 반환 합니다.

### <a name="remarks"></a>설명

키보드 드라이버에서이 멤버 함수를 반환 하는 이름을 가져옵니다. Windows에서의 지역화 된 버전의 지역화 되지 않은 키보드 드라이버를 설치할 수 있습니다 및 그 반대의 경우도 마찬가지입니다.

##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName

지정 된 가상 키 코드를 할당 하는 키의 지역화 된 이름을 가져오려면이 함수를 호출 합니다.

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>매개 변수

*vk*<br/>
가상 키 코드입니다.

*fExtended*<br/>
가상 키 코드에는 확장 된 키를 TRUE 이면 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

지정한 키의 지역화 된 이름을 합니다 *vk* 매개 변수입니다. 키에 매핑된 이름이 없는 경우 `GetKeyName` 빈 문자열을 반환 합니다.

### <a name="remarks"></a>설명

Windows에서의 지역화 된 버전의 지역화 되지 않은 키보드 드라이버를 설치할 수 있도록 키보드 드라이버에서 제공 되는이 함수가 반환 되는 키 이름 및 그 반대의 경우도 마찬가지입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey

바로 가기 키 컨트롤에 대 한 바로 가기 키를 설정합니다.

```
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>매개 변수

*wVirtualKeyCode*<br/>
[in] 바로 가기 키의 가상 키 코드입니다. 에서 표준 가상 키 코드 목록은 Winuser.h를 참조 하세요.

*wModifiers*<br/>
[in] 바로 가기 키의 한정자 키를 나타내는 플래그의 비트 조합 (OR)입니다.

보조키 플래그는 다음과 같습니다.

|플래그|해당 키|
|----------|-----------------------|
|HOTKEYF_ALT|Alt 키|
|HOTKEYF_CONTROL|CTRL 키|
|HOTKEYF_EXT|확장 된 키|
|HOTKEYF_SHIFT|Shift 키|

### <a name="remarks"></a>설명

가상 키 코드와 함께 보조키 바로 가기 키를 정의합니다.

##  <a name="setrules"></a>  CHotKeyCtrl::SetRules

잘못 된 조합이 및 바로 가기 키 컨트롤에 대 한 기본 한정자 조합을 정의 하려면이 함수를 호출 합니다.

```
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>매개 변수

*wInvalidComb*<br/>
잘못 된 키 조합을 지정 하는 플래그의 배열입니다. 다음 값의 조합 수 있습니다.

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA CTRL + ALT

- HKCOMB_NONE 수정 되지 않은 키

- HKCOMB_S SHIFT

- HKCOMB_SA SHIFT+ALT

- HKCOMB_SC SHIFT+CTRL

- HKCOMB_SCA SHIFT + CTRL + ALT

*wModifiers*<br/>
잘못 된 조합이 입력할 때 사용할 키 조합을 지정 하는 플래그의 배열입니다. 보조키 플래그에 대 한 자세한 내용은 참조 하세요. [GetHotKey](#gethotkey)합니다.

### <a name="remarks"></a>설명

에 지정 된 플래그를 통해 정의 된 대로 사용자가 잘못 된 키 조합을 입력 하는 경우 *wInvalidComb*, 시스템 OR 연산자를 사용 하 여 플래그를 지정 하 여 사용자가 입력 한 키를 결합 *wModifiers*. 결과 키 조합은 문자열로 변환 되 고 바로 가기 키 컨트롤에 표시 됩니다.

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
