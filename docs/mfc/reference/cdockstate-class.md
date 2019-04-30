---
title: CDockState 클래스
ms.date: 11/04/2016
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
ms.openlocfilehash: b8c4b80d7182795d8919adb64491d506325976ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391181"
---
# <a name="cdockstate-class"></a>CDockState 클래스

영구 메모리(파일)에서 하나 이상의 도킹 컨트롤 막대의 상태를 로드, 언로드 또는 지우는 serialize된 `CObject` 클래스입니다.

## <a name="syntax"></a>구문

```
class CDockState : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDockState::Clear](#clear)|도킹 상태 정보를 지웁니다.|
|[CDockState::GetVersion](#getversion)|저장 된 버전 번호를 검색 상태 모음입니다.|
|[CDockState::LoadState](#loadstate)|상태 레지스트리에서 정보를 검색 또는 합니다. INI 파일입니다.|
|[CDockState::SaveState](#savestate)|레지스트리 또는 INI 파일에 상태 정보를 저장합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|각 컨트롤 막대에 대해 하나의 항목을 사용 하 여 상태 정보를 고정 하는 저장 된 포인터의 배열입니다.|

## <a name="remarks"></a>설명

도킹 상태 표시줄과 도킹 여부의 위치와 크기를 포함 합니다. 때 상태를 저장 된 검색 도킹 `CDockState` 막대의 확인 위치 및 막대 현재 화면 설정으로 표시 되지 않으면 `CDockState` 표시줄의 크기를 조정 표시 되도록 배치 합니다. 주요 목적은 `CDockState` 다양 한 컨트롤 막대의 전체 상태를 저장 하 고 해당 상태를 저장할 수 있도록 하 고 레지스트리에 응용 프로그램의 하나를 로드 합니다. INI 파일 또는 이진 형식의 일부로 `CArchive` 개체의 콘텐츠입니다.

막대를 가로 막대형, 도구 모음, 상태 표시줄, 대화 상자 막대를 포함 하 여 도킹 가능한 컨트롤을 수 있습니다. `CDockState` 개체를 작성 하 고 통해 파일에서 읽거나를 `CArchive` 개체입니다.

[CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) 프레임 창의 모든 상태 정보를 검색 합니다 `CControlBar` 개체를 가져와 `CDockState` 개체입니다. 내용을 작성할 수 있습니다 합니다 `CDockState` 개체를 사용 하 여 storage [Serialize](../../mfc/reference/cobject-class.md#serialize) 또는 [CDockState::SaveState](#savestate)합니다. 나중에 프레임 창에서 컨트롤 막대의 상태를 복원 하려면 사용 하 여 상태를 로드할 수 있습니다 `Serialize` 나 [CDockState::LoadState](#loadstate)를 사용 하 여 [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) 저장을 적용할 상태 프레임 창의 컨트롤 막대입니다.

도킹 컨트롤 막대에 대 한 자세한 내용은 문서를 참조 하세요 [컨트롤 막대](../../mfc/control-bars.md), [도구 모음: 도킹 및 부동](../../mfc/docking-and-floating-toolbars.md), 및 [Windows 프레임](../../mfc/frame-windows.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>요구 사항

**헤더:** afxadv.h

##  <a name="clear"></a>  CDockState::Clear

에 저장 된 모든 도킹 정보를 지우려면이 함수를 호출 합니다 `CDockState` 개체입니다.

```
void Clear();
```

### <a name="remarks"></a>설명

여기에 뿐 아니라 막대 도킹 여부 표시줄의 크기와 위치 하지만 여부 및 표시 되는지 여부.

##  <a name="getversion"></a>  CDockState::GetVersion

저장 된 버전 번호를 검색 하려면이 함수를 호출 합니다. 상태 표시줄입니다.

```
DWORD GetVersion();
```

### <a name="return-value"></a>반환 값

1 이면 저장된 모음 정보 보다 오래 된 경우 현재 상태 표시줄 경우 2 저장된 모음 정보는 현재와 동일 하 게 상태 모음입니다.

### <a name="remarks"></a>설명

버전 지원을 통해 수정 된 막대를 새 영구 속성을 추가 및 검색 하 고 막대의 이전 버전에서 만든 영구 상태를 로드 하는 일을 할 수 있습니다.

##  <a name="loadstate"></a>  CDockState::LoadState

레지스트리에서 상태 정보를 검색 하려면이 함수를 호출 하거나 합니다. INI 파일입니다.

```
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
초기화 파일 또는 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키에서 섹션의 이름을 지정 하는 null teminated 문자열을 가리킵니다.

### <a name="remarks"></a>설명

프로필 이름에는 해당 응용 프로그램의 섹션입니다. INI 파일 또는 레지스트리 막대의 상태 정보를 포함 합니다. 컨트롤 상태 정보 막대 레지스트리에 저장할 수 있습니다 또는 합니다. INI 파일 `SaveState`합니다.

##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo

A `CPtrArray` 에서 상태 정보를 저장 하는 각 컨트롤 막대에 대 한 저장된 컨트롤 막대 정보에 대 한 포인터의 배열을 개체는 `CDockState` 개체입니다.

```
CPtrArray m_arrBarInfo;
```

##  <a name="savestate"></a>  CDockState::SaveState

상태 정보를 레지스트리에 저장 하려면이 함수를 호출 하거나 합니다. INI 파일입니다.

```
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
초기화 파일 또는 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키에서 섹션의 이름을 지정 하는 null teminated 문자열을 가리킵니다.

### <a name="remarks"></a>설명

프로필 이름에는 해당 응용 프로그램의 섹션입니다. 포함 된 INI 파일 또는 레지스트리 컨트롤 막대의 상태 정보입니다. `SaveState` 또한 현재 화면 크기를 저장합니다. 레지스트리에서 컨트롤 모음 정보를 검색할 수 있습니다 또는 합니다. INI 파일 `LoadState`합니다.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
