---
title: CMFCCmdUsageCount 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
ms.openlocfilehash: b4ad9a60831feb6fa1147ea3f8bcfd5c6badd06c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403804"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount 클래스

사용자가 메뉴에서 항목을 선택 하는 경우 같은 Windows 메시지를 사용 횟수를 추적 합니다.

## <a name="syntax"></a>구문

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|기본 생성자입니다.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCCmdUsageCount::AddCmd](#addcmd)|지정 된 명령과 사용 하 여 연결 하는 카운터가 1 씩 증가 합니다.|
|[CMFCCmdUsageCount::GetCount](#getcount)|지정 된 명령 ID와 연결 된 사용 횟수를 검색 합니다.|
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|이 개체는 최소한의 추적 데이터를 수집할지 여부를 결정 합니다.|
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|지정된 된 명령을 자주 사용 되는지 여부를 결정 합니다.|
|[CMFCCmdUsageCount::Reset](#reset)|모든 명령의 사용 횟수를 지웁니다.|
|[CMFCCmdUsageCount::Serialize](#serialize)|보관 파일에서이 개체를 읽거나 보관 파일에 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|
|[CMFCCmdUsageCount::SetOptions](#setoptions)|집합의 값을 공유 `CMFCCmdUsageCount` 클래스 데이터 멤버입니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|이름|설명|
|`m_CmdUsage`|`CMap` 명령을 해당 사용 횟수에 매핑되는 개체입니다.|
|`m_nMinUsagePercentage`|자주 사용할 명령에 대 한 최소 사용량 백분율입니다.|
|`m_nStartCount`|이 개체는 최소한의 추적 데이터를 수집할지 여부를 결정 하는 데 사용 되는 시작 카운터입니다.|
|`m_nTotalUsage`|추적 된 모든 명령의 수입니다.|

### <a name="remarks"></a>설명

`CMFCCmdUsageCount` 클래스는 32 비트 부호 없는 정수 카운터로 각 숫자 Windows 메시지 식별자를 매핑합니다. `CMFCToolBar` 이 클래스를 사용 하 여 자주 사용 하는 도구 모음 항목을 표시 합니다. 에 대 한 자세한 내용은 `CMFCToolBar`를 참조 하세요 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)합니다.

유지할 수 있습니다 `CMFCCmdUsageCount` 프로그램의 실행 간의 데이터 클래스입니다. 사용 된 [CMFCCmdUsageCount::Serialize](#serialize) 클래스 멤버 데이터를 serialize 하는 방법 및 [CMFCCmdUsageCount::SetOptions](#setoptions) 공유 멤버 데이터를 설정 하는 방법입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcmdusagecount.h

##  <a name="addcmd"></a>  CMFCCmdUsageCount::AddCmd

지정 된 명령과 사용 하 여 연결 하는 카운터가 1 씩 증가 합니다.

```
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*uiCmd*|[in] 증가 시킬 명령은 카운터를 지정 합니다.|

### <a name="remarks"></a>설명

이 메서드는 명령 개수 맵 구조에 새 항목 추가 `m_CmdUsage`이면 항목이 이미 존재 하지 않습니다.

이 메서드는 다음과 같은 경우 아무 작업도 수행 합니다.

- 이 프레임 워크 도구 모음 사용자 지정 모드는 (합니다 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) 0이 아닌 값을 반환 하는 메서드).

- 명령 참조는 하위 메뉴 또는 메뉴 구분 기호 ( *uiCmd* equals 0 또는-1).

- *uiCmd* 표준 명령 참조 (전역 `IsStandardCommand` 함수가 0이 아닌 값을 반환).

##  <a name="getcount"></a>  CMFCCmdUsageCount::GetCount

지정 된 명령 ID와 연결 된 사용 횟수를 검색 합니다.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*uiCmd*|[in] 검색할 명령 카운터의 ID입니다.|

### <a name="return-value"></a>반환 값

지정 된 명령 ID와 연결 된 사용 횟수

##  <a name="hasenoughinformation"></a>  CMFCCmdUsageCount::HasEnoughInformation

이 개체 추적 데이터의 최소 크기를 받았는지 확인 합니다.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>반환 값

이 개체는 최소한의 추적 데이터를 받은 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

경우에이 메서드는 0이 아닌 값 총 개수 `m_nTotalUsage`, 모든 추적 명령의 초기 수보다 크거나 `m_nStartCount`. 기본적으로 프레임 워크는 초기 카운트가 0을 설정합니다. 사용 하 여이 값을 재정의할 수는 [CMFCCmdUsageCount::SetOptions](#setoptions) 메서드.

이 메서드를 사용해 [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) 모든 사용 가능한 메뉴 명령이 표시 여부를 결정 합니다.

##  <a name="isfreqeuntlyusedcmd"></a>  CMFCCmdUsageCount::IsFreqeuntlyUsedCmd

지정된 된 명령을 자주 사용 되는지 여부를 결정 합니다.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*uiCmd*|[in] 확인 하는 명령을 지정 합니다.|

### <a name="return-value"></a>반환 값

0이 아닌 명령 자주 사용 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 경우 0을 반환 합니다 총 명령 사용법을 `m_nTotalUsage`은 0입니다. 이 메서드는 지정된 된 명령을 사용 되는 백분율 최소 비율을 보다 큰 경우 0이 아닌 반환이 고, 그렇지 `m_nMinUsagePercentage`합니다. 기본적으로 프레임 워크는 최소 비율을 5로 설정합니다. 사용 하 여이 값을 재정의할 수는 [CMFCCmdUsageCount::SetOptions](#setoptions) 메서드. 최소 비율을 0 이면이 메서드는 지정 된 명령 수를 0 보다 큰 경우 0이 아닌 값을 반환 합니다.

[CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) 이 메서드를 사용 하 여 명령을 거의 사용 되는지 여부를 결정 합니다.

##  <a name="reset"></a>  CMFCCmdUsageCount::Reset

모든 명령의 사용 횟수를 지웁니다.

```
void Reset();
```

### <a name="remarks"></a>설명

명령 개수 맵 구조에서 모든 항목을 삭제 하려면이 메서드를 호출 `m_CmdUsage`, 총 명령 사용법을 재설정할 수 `m_nTotalUsage`카운터를 0으로, 합니다.

##  <a name="serialize"></a>  CMFCCmdUsageCount::Serialize

이 개체는 보관 파일에서 읽거나 보관 파일에 씁니다.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*ar*|[in] `CArchive` 에서 serialize 할 개체입니다.|

### <a name="remarks"></a>설명

이 메서드는 명령 개수 맵 구조를 serialize `m_CmdUsage`, 및 총 명령 사용법을 `m_nTotalUsage`, 카운터 또는 지정 된 보관 파일에.

Serialization 예제를 보려면 [직렬화 합니다. 개체를 직렬화](../../mfc/serialization-serializing-an-object.md)합니다.

##  <a name="setoptions"></a>  CMFCCmdUsageCount::SetOptions

집합의 값을 공유 `CMFCCmdUsageCount` 클래스 데이터 멤버입니다.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*nStartCount*|[in] 모든 추적 된 명령 새 초기 수입니다.|
|*nMinUsagePercentage*|[in] 새 최소 사용량 백분율입니다.|

### <a name="return-value"></a>반환 값

메서드가 성공 하면 FALSE 경우 TRUE를 *nMinUsagePercentage* 매개 변수는 100 보다 크거나 같은 경우입니다.

### <a name="remarks"></a>설명

이 메서드는 공유 설정 `CMFCCmdUsageCount` 클래스 데이터 멤버 `m_nStartCount` 하 고 `m_nMinUsagePercentage` 하 *nStartCount* 및 *nMinUsagePercentage*각각. `m_nStartCount` 사용 되는 [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) 이 개체는 최소한의 추적 데이터를 수집할지 여부를 결정 하는 방법입니다. `m_nMinUsagePercentage` 사용 되는 [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) 지정된 된 명령 자주 사용 되는지 여부를 결정 하는 방법입니다.

디버그 빌드에서이 메서드를 어설션 실패로 경우 생성 된 *nMinUsagePercentage* 매개 변수는 100 보다 크거나 같은 경우입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)
