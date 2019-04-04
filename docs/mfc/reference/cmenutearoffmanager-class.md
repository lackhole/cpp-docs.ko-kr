---
title: CMenuTearOffManager 클래스
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: 8b92ddad9d3a6de41cf6914dee268f6e54b5d420
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776065"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager 클래스

분리 메뉴를 관리합니다. 분리 메뉴는 메뉴 모음의 메뉴입니다. 사용자는 메뉴 모음에서 분리 메뉴를 제거하여 이동 가능한 상태로 만들 수 있습니다.

   더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

## <a name="syntax"></a>구문

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|`CMenuTearOffManager` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMenuTearOffManager::Build](#build)||
|[CMenuTearOffManager::GetRegPath](#getregpath)||
|[CMenuTearOffManager::Initialize](#initialize)|초기화는 `CMenuTearOffManager` 개체입니다.|
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||
|[CMenuTearOffManager::Parse](#parse)||
|[CMenuTearOffManager::Reset](#reset)||
|[CMenuTearOffManager::SetInUse](#setinuse)||
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||

## <a name="remarks"></a>설명

응용 프로그램에서 분리 메뉴를 사용 하려면 있어야를 `CMenuTearOffManager` 개체입니다. 대부분의 경우에서 만들기 또는 초기화 하지 않습니다는 `CMenuTearOffManager` 직접 개체입니다. 이 처리를 호출 하는 경우는 [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) 함수입니다.

## <a name="example"></a>예제

다음 예제에는 생성 하 고 초기화 하는 방법을 보여 줍니다.는 `CMenuTearOffManager` 를 호출 하 여 개체를 `CWinAppEX::EnableTearOffMenus` 메서드. 이 코드 조각은 [워드 패드 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxmenutearoffmanager.h

##  <a name="build"></a>  CMenuTearOffManager::Build

```
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>매개 변수

[in] *uiTearOffBarID*<br/>

[in] *strText*<br/>

### <a name="remarks"></a>설명

##  <a name="cmenutearoffmanager"></a>  CMenuTearOffManager::CMenuTearOffManager

생성 된 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 개체입니다.

```
CMenuTearOffManager();
```

### <a name="remarks"></a>설명

대부분의 경우, 만들지 않아야는 `CMenuTearOffManager` 수동으로. 응용 프로그램의 프레임 워크를 만듭니다는 `CMenuTearOffManager` 개체를 호출할 때 [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)합니다.

##  <a name="getregpath"></a>  CMenuTearOffManager::GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="initialize"></a>  CMenuTearOffManager::Initialize

초기화 된 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 개체입니다.

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>매개 변수

*lpszRegEntry*<br/>
[in] 레지스트리 항목의 경로 포함 하는 문자열입니다. 이 레지스트리 항목에서 분리 막대가 막대에 대 한 설정을 저장 하는 응용 프로그램.

*uiTearOffMenuFirst*<br/>
[in] 분리 메뉴에 대 한 첫 번째 메뉴 ID를 지정 합니다.

*uiTearOffMenuLast*<br/>
[in] 분리 메뉴에 대 한 마지막 메뉴 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 Id 범위의 *uiTearOffMenuFirst* 하 *uiTearOffMenuLast* 연속 간격 이어야 합니다. 간격의 응용 프로그램에서 동시에 나타날 수 있는 분리 메뉴를 정의 합니다.

##  <a name="isdynamicid"></a>  CMenuTearOffManager::IsDynamicID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>매개 변수

[in] *uiID*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="parse"></a>  CMenuTearOffManager::Parse

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>매개 변수

[in] *str*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="reset"></a>  CMenuTearOffManager::Reset

```
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>매개 변수

[in] *hmenu*<br/>

### <a name="remarks"></a>설명

##  <a name="setinuse"></a>  CMenuTearOffManager::SetInUse

```
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>매개 변수

[in] *uiCmdId*<br/>

[in] *bUse*<br/>

### <a name="remarks"></a>설명

##  <a name="setuptearoffmenus"></a>  CMenuTearOffManager::SetupTearOffMenus

```
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

[in] *hMenu*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
