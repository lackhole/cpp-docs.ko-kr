---
title: DHTML 편집 명령 맵
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: 7f420619983283c225ca8fca23c5ea349def1d1b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776156"
---
# <a name="dhtml-editing-command-maps"></a>DHTML 편집 명령 맵

다음 매크로 사용 하 여 DHTML 편집 명령에 매핑할 수 있습니다 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-클래스를 파생 합니다. 사용 하는 예제를 참조 하세요 [HTMLEdit 샘플](../../overview/visual-cpp-samples.md)합니다.

### <a name="dhtml-editing-command-map-macros"></a>DHTML 편집 명령 맵 매크로

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|DHTML 편집 명령에에서 있는 map 클래스를 선언합니다.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|DHTML 편집 명령 맵 클래스 내에서 정의 시작합니다.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML 편집 명령 맵의 끝을 표시 합니다.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|HTML 편집 명령에 명령 ID를 매핑합니다.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|HTML 편집 명령 및 메시지 처리기 명령 ID를 매핑합니다.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|명령 ID를 HTML 편집 명령 및 사용자 인터페이스 요소로 매핑됩니다.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|명령 ID를 HTML 편집 명령, 메시지 처리기 및 사용자 인터페이스 요소로 매핑합니다.|

##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP

DHTML 편집 명령에에서 있는 map 클래스를 선언합니다.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
클래스의 이름입니다.

### <a name="remarks"></a>설명

이 매크로의 정의에 사용 하는 것 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-클래스를 파생 합니다.

사용 하 여 [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) 지도 구현 합니다.

### <a name="example"></a>예제

참조 [HTMLEdit 샘플](../../overview/visual-cpp-samples.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP

DHTML 편집 명령 맵 클래스 내에서 정의 시작합니다.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>매개 변수

*className*<br/>
DHTML 편집 명령 맵을 포함 하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) 등과 합니다 [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) 해당 클래스 정의 내에서 매크로입니다.

### <a name="remarks"></a>설명

DHTML 편집 명령 맵 사용자 인터페이스 명령 HTML 편집 명령에 매핑할 클래스에 추가 합니다.

BEGIN_DHTMLEDITING_CMDMAP 매크로 뒤에 클래스의 구현 (.cpp) 파일에 배치 [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) 클래스 (예: IDM_CUT ID_EDIT_CUT)에서 매핑할는 명령에 대 한 매크로입니다. 사용 된 [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) 이벤트 map의 끝을 표시 하는 매크로입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP

DHTML 편집 명령 맵의 끝을 표시 합니다.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>설명

과 함께 사용할 [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)합니다.

### <a name="example"></a>예제

참조 [HTMLEdit 샘플](../../overview/visual-cpp-samples.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY

HTML 편집 명령에 명령 ID를 매핑합니다.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
(예: ID_EDIT_COPY) 명령 ID입니다.

*dhtmlcmdID*<br/>
HTML 편집 명령 *cmdID* (예: IDM_COPY) 매핑합니다.

### <a name="example"></a>예제

참조 [HTMLEdit 샘플](../../overview/visual-cpp-samples.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC

HTML 편집 명령 및 메시지 처리기 명령 ID를 매핑합니다.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
(예: ID_EDIT_COPY) 명령 ID입니다.

*dhtmlcmdID*<br/>
HTML 편집 명령 *cmdID* (예: IDM_COPY) 매핑합니다.

*member_func_name*<br/>
명령이 매핑되는 메시지-처리기 함수의 이름입니다.

### <a name="example"></a>예제

참조 [HTMLEdit 샘플](../../overview/visual-cpp-samples.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE

명령 ID를 HTML 편집 명령 및 사용자 인터페이스 요소로 매핑됩니다.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
(예: ID_EDIT_COPY) 명령 ID입니다.

*dhtmlcmdID*<br/>
HTML 편집 명령 *cmdID* (예: IDM_COPY) 매핑합니다.

*elemType*<br/>
사용자 인터페이스 요소 형식입니다. AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX, 또는 AFX_UI_ELEMTYPE_RADIO 중 하나입니다.

### <a name="example"></a>예제

참조 [HTMLEdit 샘플](../../overview/visual-cpp-samples.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

명령 ID를 HTML 편집 명령, 메시지 처리기 및 사용자 인터페이스 요소로 매핑합니다.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
(예: ID_EDIT_COPY) 명령 ID입니다.

*dhtmlcmdID*<br/>
HTML 편집 명령 *cmdID* (예: IDM_COPY) 매핑합니다.

*member_func_name*<br/>
명령이 매핑되는 메시지-처리기 함수의 이름입니다.

*elemType*<br/>
사용자 인터페이스 요소 형식입니다. AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX, 또는 AFX_UI_ELEMTYPE_RADIO 중 하나입니다.

### <a name="example"></a>예제

참조 [HTMLEdit 샘플](../../overview/visual-cpp-samples.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
