---
title: CIPAddressCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
ms.openlocfilehash: 5abcf838308d8965f3c55dc7d85dbac974825394
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392598"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl 클래스

Windows의 공용 IP 주소 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|`CIPAddressCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CIPAddressCtrl::ClearAddress](#clearaddress)|IP 주소 컨트롤의 내용을 지웁니다.|
|[CIPAddressCtrl::Create](#create)|IP 주소 컨트롤을 만들고 연결 하는 `CIPAddressCtrl` 개체입니다.|
|[CIPAddressCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 IP 주소 컨트롤을 만들고에 연결 된 `CIPAddressCtrl` 개체입니다.|
|[CIPAddressCtrl::GetAddress](#getaddress)|IP 주소 컨트롤의 모든 4 개의 필드에 대 한 주소 값을 검색합니다.|
|[CIPAddressCtrl::IsBlank](#isblank)|IP 주소 컨트롤의 모든 필드가 비어 있는 경우를 결정 합니다.|
|[CIPAddressCtrl::SetAddress](#setaddress)|IP 주소 컨트롤의 모든 4 개의 필드에 대 한 주소 값을 설정합니다.|
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|IP 주소 컨트롤의 지정된 된 필드에 키보드 포커스를 설정 합니다.|
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|IP 주소 컨트롤의 지정된 된 필드에 범위를 설정합니다.|

## <a name="remarks"></a>설명

컨트롤의 편집 컨트롤을 비슷하게 IP 주소 컨트롤을 입력 하 고 IP (인터넷 프로토콜) 형식으로 숫자 주소를 조작할 수 있습니다.

이 컨트롤 (및 따라서는 `CIPAddressCtrl` 클래스)에서 Microsoft Internet Explorer 4.0 이상 실행 되는 프로그램에만 사용할 수입니다. 또한 이후 버전의 Windows 및 Windows NT에서 제공 됩니다.

IP 주소 컨트롤에 대 한 자세한 내용은 참조 하세요. [IP 주소 컨트롤](/windows/desktop/Controls/ip-address-controls) Windows SDK에 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="cipaddressctrl"></a>  CIPAddressCtrl::CIPAddressCtrl

`CIPAddressCtrl` 개체를 만듭니다.

```
CIPAddressCtrl();
```

##  <a name="clearaddress"></a>  CIPAddressCtrl::ClearAddress

IP 주소 컨트롤의 내용을 지웁니다.

```
void ClearAddress();
```

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_CLEARADDRESS](/windows/desktop/Controls/ipm-clearaddress)Windows SDK에 설명 된 대로 합니다.

##  <a name="create"></a>  CIPAddressCtrl::Create

IP 주소 컨트롤을 만들고 연결 하는 `CIPAddressCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
IP 주소 컨트롤의 스타일입니다. 창 스타일의 조합을 적용 됩니다. 컨트롤을 자식 창에 있어야 하므로 WS_CHILD 스타일을 포함 해야 합니다. 참조 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) windows 스타일의 목록은 Windows SDK에 있습니다.

*rect*<br/>
IP 주소 컨트롤의 크기와 위치에 대 한 참조입니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조입니다.

*pParentWnd*<br/>
IP 주소 컨트롤의 부모 창에 대 한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
IP 주소 컨트롤의 id입니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CIPAddressCtrl` 두 단계에서 개체입니다.

1. 만드는 생성자를 호출 합니다 `CIPAddressCtrl` 개체입니다.

1. 호출 `Create`, IP 주소 컨트롤 만듭니다.

컨트롤을 사용 하 여 확장된 창 스타일을 사용 하려는 경우 호출할 [CreateEx](#createex) 대신 `Create`합니다.

##  <a name="createex"></a>  CIPAddressCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 하려면이 함수를 호출 합니다 `CIPAddressCtrl` 개체입니다.

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
IP 주소 컨트롤의 스타일입니다. 창 스타일의 조합을 적용 됩니다. 컨트롤을 자식 창에 있어야 하므로 WS_CHILD 스타일을 포함 해야 합니다. 참조 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) windows 스타일의 목록은 Windows SDK에 있습니다.

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

##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress

IP 주소 컨트롤의 모든 4 개의 필드에 대 한 주소 값을 검색합니다.

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>매개 변수

*nField0*<br/>
압축 된 IP 주소에서 0 필드 값에 대 한 참조입니다.

*nField1*<br/>
압축 된 IP 주소에서 1 필드 값에 대 한 참조입니다.

*nField2*<br/>
압축 된 IP 주소에서 2 필드 값에 대 한 참조입니다.

*nField3*<br/>
압축 된 IP 주소의 3 필드 값에 대 한 참조입니다.

*dwAddress*<br/>
IP 주소를 수신 하는 DWORD 값의 주소에 대 한 참조입니다. 참조 **주의** 표시 하는 테이블에 대 한 방법을 *dwAddress* 채워집니다.

### <a name="return-value"></a>반환 값

IP 주소 컨트롤의 공백이 아닌 필드 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_GETADDRESS](/windows/desktop/Controls/ipm-getaddress)Windows SDK에 설명 된 대로 합니다. 위의 첫 번째 프로토타입 읽기 숫자 0부터 컨트롤의 3까지 필드를 왼쪽에서 오른쪽 각각에서 4 개의 매개 변수를 채웁니다. 위의 두 번째 프로토타입에서 *dwAddress* 다음과 같이 채워집니다.

|필드|필드 값이 포함 된 비트|
|-----------|-------------------------------------|
|0|부터 31 까지의 24|
|1|부터 23 까지의 16|
|2|8 ~ 15|
|3|0 ~ 7|

##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank

IP 주소 컨트롤의 모든 필드가 비어 있는 경우를 결정 합니다.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>반환 값

모든 경우에 0이 아닌 IP 주소 컨트롤의 필드가 비어 있습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_ISBLANK](/windows/desktop/Controls/ipm-isblank)Windows SDK에 설명 된 대로 합니다.

##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress

IP 주소 컨트롤의 모든 4 개의 필드에 대 한 주소 값을 설정합니다.

```
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>매개 변수

*nField0*<br/>
압축 된 IP 주소에서 0 필드 값입니다.

*nField1*<br/>
압축 된 IP 주소에서 1 필드 값입니다.

*nField2*<br/>
압축 된 IP 주소를 2 필드 값입니다.

*nField3*<br/>
압축 된 IP 주소의 3 필드 값입니다.

*dwAddress*<br/>
새 IP 주소를 포함 하는 DWORD 값입니다. 참조 **주의** DWORD 값을 채우는 방법을 보여 주는 테이블입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_SETADDRESS](/windows/desktop/Controls/ipm-setaddress)Windows SDK에 설명 된 대로 합니다. 위의 첫 번째 프로토타입 읽기 숫자 0부터 컨트롤의 3까지 필드를 왼쪽에서 오른쪽 각각에서 4 개의 매개 변수를 채웁니다. 위의 두 번째 프로토타입에서 *dwAddress* 다음과 같이 채워집니다.

|필드|필드 값이 포함 된 비트|
|-----------|-------------------------------------|
|0|부터 31 까지의 24|
|1|부터 23 까지의 16|
|2|8 ~ 15|
|3|0 ~ 7|

##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus

IP 주소 컨트롤의 지정된 된 필드에 키보드 포커스를 설정 합니다.

```
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>매개 변수

*nField*<br/>
포커스를 설정 해야 할 0부터 시작 필드 인덱스입니다. 이 값 필드의 수보다 큰 경우 첫 번째 빈 필드에 포커스가 설정 됩니다. 모든 필드가 비어 있지 않은 경우 첫 번째 필드에 포커스가 설정 됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_SETFOCUS](/windows/desktop/Controls/ipm-setfocus)Windows SDK에 설명 된 대로 합니다.

##  <a name="setfieldrange"></a>  CIPAddressCtrl::SetFieldRange

IP 주소 컨트롤의 지정된 된 필드에 범위를 설정합니다.

```
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>매개 변수

*nField*<br/>
범위를 적용할 수는 0부터 시작 필드 인덱스입니다.

*nLower*<br/>
이 IP 주소 컨트롤에서 지정된 된 필드의 하한값을 수신 하는 정수에 대 한 참조입니다.

*nUpper*<br/>
이 IP 주소 컨트롤에서 지정된 된 필드의 상한값을 수신 하는 정수에 대 한 참조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_SETRANGE](/windows/desktop/Controls/ipm-setrange)Windows SDK에 설명 된 대로 합니다. 두 매개 변수를 사용 하 여 *nLower* 하 고 *nUpper*대신 필드의 아래쪽과 위쪽 한계를 나타내기 위해 합니다 *wRange* Win32 메시지를 사용 하는 매개 변수.

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
