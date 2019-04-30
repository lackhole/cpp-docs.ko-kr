---
title: CNetAddressCtrl 클래스
ms.date: 11/19/2018
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
ms.openlocfilehash: ec4d7aa6f2a1061e632b81a27a0233cf5fdd1c63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373822"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl 클래스

`CNetAddressCtrl` 클래스에 입력 한 IPv4, IPv6 및 DNS 주소를 이름이 지정된 형식의 유효성을 검사하는 데 사용할 수 있는 네트워크 주소 컨트롤을 나타냅니다.

## <a name="syntax"></a>구문

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|`CNetAddressCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CNetAddressCtrl::Create](#create)|지정 된 스타일을 사용 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.|
|[CNetAddressCtrl::CreateEx](#createex)|지정 된 확장된 스타일을 사용 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|사용자가 현재 네트워크 주소 컨트롤에서 지원 되지 않는 네트워크 주소를 입력 하는 경우는 오류 풍선을 표시 합니다.|
|[CNetAddressCtrl::GetAddress](#getaddress)|현재 네트워크 주소 컨트롤을 사용 하 여 연결 된 네트워크 주소의 유효성을 검사 하 고 구문 분석 된 표현을 검색 합니다.|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 검색 합니다.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 설정 합니다.|

## <a name="remarks"></a>설명

네트워크 주소 컨트롤 사용자가 입력 주소 형식이 올바른지 확인 합니다. 컨트롤의 네트워크 주소에 실제로 연결 하지 않습니다. [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드 주소 하나 이상의 유형을 지정 하는 합니다 [CNetAddressCtrl::GetAddress](#getaddress) 메서드 구문 분석 하 고 확인할 수. 주소는 IPv4, IPv6, 또는 서버, 네트워크, 호스트 또는 브로드캐스트 메시지 대상에 대 한 명명 된 주소 형식의 수 있습니다. 주소 형식이 올바르지 않으면를 사용할 수는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 미리 정의 된 표시를 그래픽으로 네트워크 주소 컨트롤의 텍스트 상자를 가리키는 infotip 메시지 상자를 표시 하는 방법 오류 메시지입니다.

합니다 `CNetAddressCtrl` 에서 파생 된 클래스를 [CEdit](../../mfc/reference/cedit-class.md) 클래스입니다. 따라서 네트워크 주소 컨트롤 모든 Windows 편집 컨트롤 메시지에 대 한 액세스를 제공합니다.

다음 그림은 네트워크 주소 컨트롤이 포함 된 대화 상자를 보여 줍니다. 텍스트 상자 (1) 네트워크 주소 컨트롤에 대 한 잘못 된 네트워크 주소를 포함합니다. 정보 팁 메시지 (2)는 네트워크 주소가 유효 하지 않은 경우에 표시 됩니다.

![네트워크 주소 컨트롤 및 정보 팁을 사용 하 여 대화 상자. ](../../mfc/reference/media/cnetaddctrl.png "네트워크 주소 컨트롤 및 정보 팁을 사용 하 여 대화 상자.")

## <a name="example"></a>예제

다음 코드 예제는 네트워크 주소의 유효성을 검사 하는 대화의 일부입니다. 세 개의 라디오 단추에 대 한 이벤트 처리기 지정 네트워크 주소 세 가지 주소 유형 중 하나일 수 있습니다. 사용자가 네트워크 컨트롤의 텍스트 상자에 주소를 입력 한 다음 주소를 확인 하는 단추를 누를 합니다. 주소가 올바르면 성공 메시지가 표시 됩니다. 그렇지 않으면 미리 정의 된 정보 팁 오류 메시지가 표시 됩니다.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>예제

대화 헤더 파일에서 다음 코드 예제에서는 정의 [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) 하 고 [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) 에 필요한 변수를 [CNetAddressCtrl::GetAddress](#getaddress)메서드.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

이 클래스는 Windows Vista 이상 사용할 수 있습니다.

이 클래스에 대 한 추가 요구 사항에 설명 되어 [빌드 요구 사항에 대 한 Windows Vista 공용 컨트롤](../../mfc/build-requirements-for-windows-vista-common-controls.md)합니다.

##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl

`CNetAddressCtrl` 개체를 생성합니다.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>설명

사용 된 [CNetAddressCtrl::Create](#create) 또는 [CNetAddressCtrl::CreateEx](#createex) 네트워크 제어를 만들고 연결 하는 메서드를 `CNetAddressCtrl` 개체.

##  <a name="create"></a>  CNetAddressCtrl::Create

지정 된 스타일을 사용 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwStyle*|[in] 컨트롤에 적용 될 스타일의 비트 조합입니다. 자세한 내용은 [스타일 편집](../../mfc/reference/styles-used-by-mfc.md#edit-styles)합니다.|
|*rect*|[in] 에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|
|*pParentWnd*|[in] 에 대 한 null이 아닌 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다.|
|*nID*|[in] 컨트롤의 ID입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="createex"></a>  CNetAddressCtrl::CreateEx

지정 된 확장된 스타일을 사용 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwExStyle*|[in] 컨트롤에 적용 될 확장된 스타일의 비트 조합 (OR)입니다. 자세한 내용은 참조는 *dwExStyle* 의 매개 변수를 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) 함수입니다.|
|*dwStyle*|[in] 컨트롤에 적용 될 스타일의 비트 조합 (OR)입니다. 자세한 내용은 [스타일 편집](../../mfc/reference/styles-used-by-mfc.md#edit-styles)합니다.|
|*rect*|[in] 에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|
|*pParentWnd*|[in] 에 대 한 null이 아닌 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다.|
|*nID*|[in] 컨트롤의 ID입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip

현재 네트워크 주소 컨트롤을 사용 하 여 연결 된 풍선 팁에는 오류 메시지를 표시 합니다.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>반환 값

값 `S_OK` , 그렇지 않으면이 메서드는 경우 오류 코드입니다.

### <a name="remarks"></a>설명

사용 된 [CNetAddressCtrl::SetAllowType](#setallowtype) 현재 네트워크 주소 컨트롤을 지원할 수 있는 주소 유형을 지정 하는 방법입니다. 사용 된 [CNetAddressCtrl::GetAddress](#getaddress) 의 유효성을 검사 하 고 사용자가 입력 하는 네트워크 주소를 구문 분석 방법입니다. 사용 합니다 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 하는 경우 오류 메시지 정보 팁을 표시 하는 메서드를 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 성공적으로 수행 되지 합니다.

이 메시지를 호출 하는 [NetAddr_DisplayErrorTip](/windows/desktop/api/shellapi/nf-shellapi-netaddr_displayerrortip) Windows SDK에 설명 된 매크로입니다. 매크로 보냅니다는 `NCM_DISPLAYERRORTIP` 메시지입니다.

##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress

현재 네트워크 주소 컨트롤을 사용 하 여 연결 된 네트워크 주소의 유효성을 검사 하 고 구문 분석 된 표현을 검색 합니다.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>매개 변수

*pAddress*<br/>
[out에서] 에 대 한 포인터를 [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) 구조입니다.  설정 된 *pAddrInfo* 주소로이 구조체의 멤버는 [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) GetAddress 메서드를 호출 하기 전에 구조체입니다.

### <a name="return-value"></a>반환 값

이 메서드가 성공 하면 s_ok이 고, 값 그렇지 않으면 COM 오류 코드입니다. 가능한 오류 코드에 대 한 자세한 내용은의 반환 값 섹션을 참조 합니다 [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) 매크로입니다.

### <a name="remarks"></a>설명

이 메서드는 성공 하는 경우는 [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) 구조 네트워크 주소에 대 한 추가 정보를 포함 합니다.

사용 된 [CNetAddressCtrl::SetAllowType](#setallowtype) 현재 네트워크 주소 컨트롤 수 주소의 형식을 지정 하는 방법입니다. 사용 된 [CNetAddressCtrl::GetAddress](#getaddress) 의 유효성을 검사 하 고 사용자가 입력 하는 네트워크 주소를 구문 분석 방법입니다. 사용 합니다 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 하는 경우 오류 메시지 정보 팁을 표시 하는 메서드를 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 성공적으로 수행 되지 합니다.

이 메서드를 호출 하는 [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) Windows SDK에 설명 된 매크로입니다. 매크로는 NCM_GETADDRESS 메시지를 보냅니다.

##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType

현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 검색 합니다.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>반환 값

비트 조합 (OR) 플래그 주소의 형식을 지정 하는 네트워크 주소 컨트롤을 지원할 수 있습니다. 자세한 내용은 [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586)합니다.

### <a name="remarks"></a>설명

이 메시지를 호출 하는 [NetAddr_GetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getallowtype) Windows SDK에 설명 된 매크로입니다. 매크로는 NCM_GETALLOWTYPE 메시지를 보냅니다.

##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType

현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 설정 합니다.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwAddrMask*|[in] 비트 조합 (OR) 플래그 주소의 형식을 지정 하는 네트워크 주소 컨트롤을 지원할 수 있습니다. 자세한 내용은 [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586)합니다.|

### <a name="return-value"></a>반환 값

이 메서드가 성공 하면 s_ok이 고 그렇지 않으면 COM 오류 코드입니다.

### <a name="remarks"></a>설명

사용 된 [CNetAddressCtrl::SetAllowType](#setallowtype) 현재 네트워크 주소 컨트롤을 지원할 수 있는 주소 유형을 지정 하는 방법입니다. 사용 된 [CNetAddressCtrl::GetAddress](#getaddress) 의 유효성을 검사 하 고 사용자가 입력 하는 네트워크 주소를 구문 분석 방법입니다. 사용 합니다 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 하는 경우 오류 메시지 정보 팁을 표시 하는 메서드를 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 성공적으로 수행 되지 합니다.

이 메시지를 호출 하는 [NetAddr_SetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_setallowtype) Windows SDK에 설명 된 매크로입니다. 매크로는 NCM_SETALLOWTYPE 메시지를 보냅니다.

## <a name="see-also"></a>참고자료

[CNetAddressCtrl 클래스](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)
