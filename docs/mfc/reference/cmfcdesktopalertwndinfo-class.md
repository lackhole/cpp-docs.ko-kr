---
title: CMFCDesktopAlertWndInfo 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: a4b3d8769b3d267c0bd3f81269dd3b8ab3cf3184
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768291"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo 클래스

합니다 `CMFCDesktopAlertWndInfo` 클래스를 사용 합니다 [CMFCDesktopAlertWnd 클래스](../../mfc/reference/cmfcdesktopalertwnd-class.md)합니다. 바탕 화면 경고 창이 표시될 경우 표시되는 컨트롤을 지정합니다.

## <a name="syntax"></a>구문

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::operator=](#operator_eq)||

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|표시 되는 아이콘에 대 한 핸들입니다.|
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|바탕 화면 알림 창에서 링크와 관련 된 명령 ID입니다.|
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|바탕 화면 경고 창에 표시 되는 텍스트입니다.|
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|바탕 화면 경고 창에 표시 되는 링크입니다.|

## <a name="remarks"></a>설명

합니다 `CMFCDesktopAlertWndInfo` 클래스에 전달 되는 [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 바탕 화면 경고 창이의 기본 대화 상자에 표시 되는 요소를 지정 하는 방법입니다. 기본 대화 상자는 세 가지 항목을 포함할 수 있습니다.

- 호출 하 여 설정 된 아이콘 [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)합니다.

- 레이블 또는 호출 하 여 설정 된 문자 메시지 [CMFCDesktopAlertWndInfo::m_strText](#m_strtext)합니다.

- 링크를 호출 하 여 설정 된 [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)합니다. 설정 링크를 클릭할 때 실행 되는 명령, 호출 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)합니다.

기본 대화 상자에 충분 하지 않으면 만들기 사용자 지정 대화 상자를에 전달 된 [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 이 클래스를 사용 하는 대신 메서드. 자세한 내용은 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 다양 한 멤버를 사용 하는 방법에 설명 합니다 `CMFCDesktopAlertWndInfo` 클래스입니다. 예제에는 바탕 화면 경고 창이, 바탕 화면 경고 창에 표시 되는 링크 및 바탕 화면 경고 창이에서 링크를 사용 하 여 연결 된 명령 ID에 표시 되는 텍스트 아이콘 표시 되는 핸들을 설정 하는 방법을 보여 줍니다. 이 예제는의 일부를 [바탕 화면 경고 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDesktopAlertDialog.h

##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator=

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>매개 변수

[in] *src*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="m_hicon"></a>  CMFCDesktopAlertWndInfo::m_hIcon

표시 되는 아이콘에 대 한 핸들입니다.

```
HICON m_hIcon;
```

### <a name="remarks"></a>설명

##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID

바탕 화면 알림 창에서 링크와 관련 된 명령 ID입니다.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>설명

명령 ID를 사용자 지정 된 링크를 클릭할 때 팝업 창의 소유자에 게 전송 됩니다 [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)합니다.

##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText

바탕 화면 경고 창에 표시 되는 텍스트입니다.

```
CString m_strText;
```

### <a name="remarks"></a>설명

##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL

바탕 화면 경고 창에 표시 되는 링크입니다.

```
CString m_strURL;
```

### <a name="remarks"></a>설명

사용자가 링크를 클릭 하면 명령이 포함 된 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) 명령 ID가 팝업 창의 소유자에 게 전송 됩니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)
