---
title: COleCmdUI 클래스
ms.date: 09/12/2018
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
ms.openlocfilehash: 5dc4e9504805146a9eff0f5ab937868226e4516e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148512"
---
# <a name="colecmdui-class"></a>COleCmdUI 클래스

애플리케이션의 `IOleCommandTarget`기반 기능과 관련된 사용자 인터페이스 개체의 상태를 업데이트하기 위한 MFC용 메서드를 구현합니다.

## <a name="syntax"></a>구문

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleCmdUI::COleCmdUI](#colecmdui)|`COleCmdUI` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleCmdUI::Enable](#enable)|설정 하거나 사용 명령 플래그를 지웁니다.|
|[COleCmdUI::SetCheck](#setcheck)|상태를 설정/해제 설정/해제를 설정 하는 명령입니다.|
|[COleCmdUI::SetText](#settext)|명령에 대 한 텍스트 이름 또는 상태 문자열을 반환합니다.|

## <a name="remarks"></a>설명

응용 프로그램에서 사용 되지 않는 DocObjects에 대 한 MFC 응용 프로그램에서 메뉴를 사용자에 게 보이는 UPDATE_COMMAND_UI 사람은 처리 하는 경우. 각 알림에 지정 하는 한 [CCmdUI](../../mfc/reference/ccmdui-class.md) 특정 명령의 상태를 반영 하도록 조작할 수 있는 개체입니다. 그러나 응용 프로그램은 DocObjects을 사용할 경우 MFC UPDATE_OLE_COMMAND_UI 알림을 처리 하 고 할당 `COleCmdUI` 개체입니다.

`COleCmdUI` 해당 컨테이너의 사용자 인터페이스 (예: FileNew, 열기, 인쇄 및 등)에서 발생 하는 명령을 수신 하도록 DocObject을 DocObject의 사용자 인터페이스에서 발생 하는 명령을 수신 하는 컨테이너 수 있도록 합니다. 하지만 `IDispatch` 과 동일한 명령을 발송 하는 데 사용할 수 있습니다 `IOleCommandTarget` 쿼리하고 인수 없이 일반적으로 명령의 표준 집합을 사용 및 형식 정보가 없는 관련 되어 있으므로 실행 하는 간단한 방법을 제공 합니다. `COleCmdUI` 사용 하도록 설정, 업데이트 및 DocObject 사용자 인터페이스 명령의 기타 속성 설정에 사용할 수 있습니다. 명령을 호출 하려는 경우 호출할 [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)합니다.

참조에 대 한 자세한 내용은 DocObjects [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) 하 고 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>요구 사항

**헤더:** afxdocobj.h

##  <a name="colecmdui"></a>  COleCmdUI::COleCmdUI

생성 된 `COleCmdUI` 특정 사용자 인터페이스 명령과 연결 된 개체입니다.

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>매개 변수

*rgCmds*<br/>
지원 되는 명령의 목록을 지정한 GUID와 사용 하 여 연결 합니다. `OLECMD` 구조체 명령 플래그를 사용 하 여 명령을 연결 합니다.

*cCmds*<br/>
명령 수 *rgCmds*합니다.

*pGroup*<br/>
명령 집합을 식별 하는 GUID에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`COleCmdUI` 개체는 메뉴 항목 또는 컨트롤 막대 단추와 같은 DocObject 사용자 인터페이스 개체 업데이트에 대 한 프로그래밍 인터페이스를 제공 합니다. 사용자 인터페이스 개체를 사용 하도록 설정, 사용 하지 않도록 설정,이 옵션을 선택 하거나 통해 수 수를 `COleCmdUI` 개체입니다.

##  <a name="enable"></a>  COleCmdUI::Enable

명령 플래그를 설정 하려면이 함수를 호출 합니다 `COleCmdUI` OLECOMDF_ENABLED 알리는 인터페이스 명령을 사용할 수 있으며 사용, 또는 명령 플래그를 지우려면 개체입니다.

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>매개 변수

*bOn*<br/>
연결 된 명령을 여부를 나타냅니다는 `COleCmdUI` 개체를 사용 하도록 설정 하거나 사용 하지 않도록 설정 해야 합니다. Nonzero; 명령을 사용 하도록 설정 0 명령을 사용 하지 않도록 설정 합니다.

##  <a name="setcheck"></a>  COleCmdUI::SetCheck

설정/해제 설정/해제 상태를 설정 하려면이 함수 호출 명령입니다.

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>매개 변수

*nCheck*<br/>
설정/해제 설정/해제를 설정할 상태를 확인 하는 값 명령입니다. 값:

|값|설명|
|-----------|-----------------|
|**1**|명령을 설정합니다.|
|**2**|비활성화; 명령을 설정합니다 특성이 이므로이 명령에서 관련 된 선택의 상태를 off 상태를 확인할 수 없습니다.|
|다른 값|해제 하는 명령을 설정 합니다.|

##  <a name="settext"></a>  COleCmdUI::SetText

명령에 대 한 텍스트 이름 또는 상태 문자열을 반환 하려면이 함수를 호출 합니다.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
명령을 사용 하 여 사용할 텍스트 포인터입니다.

## <a name="see-also"></a>참고자료

[CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
