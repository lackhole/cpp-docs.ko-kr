---
title: CRecentFileList 클래스
ms.date: 11/04/2016
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
ms.openlocfilehash: 30536d91d057de4e551b5a28200dd903e12713b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372181"
---
# <a name="crecentfilelist-class"></a>CRecentFileList 클래스

MRU(가장 최근에 사용됨) 파일 목록의 컨트롤을 지원합니다.

## <a name="syntax"></a>구문

```
class CRecentFileList
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRecentFileList::CRecentFileList](#crecentfilelist)|`CRecentFileList` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRecentFileList::Add](#add)|최근에 사용한 파일 목록에 파일을 추가합니다.|
|[CRecentFileList::GetDisplayName](#getdisplayname)|메뉴 표시는 최근에 사용한 파일 이름에 대 한 표시 이름을 제공합니다.|
|[CRecentFileList::GetSize](#getsize)|최근에 사용한 파일 목록에 파일을 검색합니다.|
|[CRecentFileList::ReadList](#readlist)|레지스트리에서 최근에 사용한 파일 목록을 읽습니다 또는 합니다. INI 파일입니다.|
|[CRecentFileList::Remove](#remove)|최근에 사용한 파일 목록에서 파일을 제거 합니다.|
|[CRecentFileList::UpdateMenu](#updatemenu)|최근에 사용한 파일 목록 메뉴 표시를 업데이트합니다.|
|[CRecentFileList::WriteList](#writelist)|레지스트리에서 최근에 사용한 파일 목록을 작성 또는 합니다. INI 파일입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CRecentFileList::operator \[ \]](#operator_at)|반환 된 `CString` 지정 된 위치에 있는 개체입니다.|

## <a name="remarks"></a>설명

파일에 추가 하거나 최근에 사용한 파일 목록에서 삭제할 수, 파일 목록에서 읽거나 수 레지스트리에 기록 된 또는 합니다. INI 파일 및 최근에 사용한 파일 목록을 표시 하 고 메뉴를 업데이트할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CRecentFileList`

## <a name="requirements"></a>요구 사항

**헤더:** afxadv.h

##  <a name="add"></a>  CRecentFileList::Add

가장 최근에 사용한 (MRU) 파일 목록에 파일을 추가합니다.

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
목록에 추가할 경로 지정 합니다.

*lpszAppID*<br/>
응용 프로그램에 대 한 응용 프로그램 사용자 모델 ID를 지정합니다.

*pItem*<br/>
목록에 추가할 셸 항목에 대 한 포인터를 지정 합니다.

*pLink*<br/>
목록에 추가할 셸 링크에 대 한 포인터를 지정 합니다.

*pidl*<br/>
최근 docs 폴더에 추가 해야 하는 셸 항목에 대 한 IDLIST를 지정 합니다.

### <a name="remarks"></a>설명

파일 이름은 MRU 목록의 맨 위에 추가 됩니다. 파일 이름에 이미 있으면 MRU 목록의 맨 위로 이동 됩니다.

##  <a name="crecentfilelist"></a>  CRecentFileList::CRecentFileList

`CRecentFileList` 개체를 생성합니다.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>매개 변수

*nStart*<br/>
MRU (가장 최근에 사용한) 파일 목록 메뉴 표시에 번호 매기기에 대 한 오프셋입니다.

*lpszSection*<br/>
레지스트리 또는 응용 프로그램의 섹션의 이름 가리킵니다. INI 파일 최근에 사용한 파일 목록은 읽거나 기록 하는 위치입니다.

*lpszEntryFormat*<br/>
레지스트리 또는 응용 프로그램에 저장 된 항목의 이름에 사용할 형식 문자열을 가리킵니다. INI 파일입니다.

*nSize*<br/>
최근에 사용한 파일 목록에 있는 파일의 최대 수입니다.

*nMaxDispLen*<br/>
최근에 사용한 파일 목록에 파일 이름 메뉴 표시에 사용할 수 있는 문자는 최대 길이입니다.

### <a name="remarks"></a>설명

가리키는 형식 문자열 *lpszEntryFormat* 각 MRU 항목의 인덱스를 대체에 사용할 "%d"를 포함 해야 합니다. 예를 들어 형식 문자열 `"file%d"` 항목의 이름은 다음 `file0`, `file1`등입니다.

##  <a name="getdisplayname"></a>  CRecentFileList::GetDisplayName

MRU 목록 메뉴 표시에 사용 하기 위해 최근에 사용한 파일 목록에서 파일에 대 한 표시 이름을 가져옵니다.

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
이름이 MRU 파일 메뉴 목록에 표시 되는 파일의 전체 경로입니다.

*nIndex*<br/>
최근에 사용한 파일 목록에 파일의 0부터 시작 인덱스입니다.

*lpszCurDir*<br/>
현재 디렉터리를 포함 하는 문자열입니다.

*nCurDir*<br/>
현재 디렉터리 문자열의 길이입니다.

*bAtLeastName*<br/>
0이 아니면 파일의 기본 이름 해야 반환 되어야 함을 나타냅니다, 최대 표시 길이 초과 하는 경우에 (변수로 전달 된 *nMaxDispLen* 매개 변수를는 `CRecentFileList` 생성자).

### <a name="return-value"></a>반환 값

**FALSE** 가장 최근에 사용한 (MRU) 파일 목록에 지정된 된 인덱스에 없는 파일 이름이 없으면입니다.

### <a name="remarks"></a>설명

파일이 현재 디렉터리에 있으면 함수 표시 해제 디렉터리를 유지 합니다. 파일 이름이 너무 긴 경우 디렉터리 및 확장명을 제거 됩니다. 하지 않는 한 표시 이름이 빈 문자열로 설정 파일 이름이 여전히 너무 긴 경우 *bAtLeastName* 0이 아닌 합니다.

##  <a name="getsize"></a>  CRecentFileList::GetSize

최근에 사용한 파일 목록에 파일을 검색합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>반환 값

현재에서 파일 수에는 가장 최근에 (사용한 MRU) 파일 목록 사용.

##  <a name="operator_at"></a>  CRecentFileList::operator [ ]

오버 로드 된 첨자 (`[]`) 연산자는 단일 반환 `CString` 의 0부터 시작 하는 인덱스로 지정 된 *nIndex*합니다.

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
0 기반 인덱스를 `CString` 집합이 `CString`s입니다.

##  <a name="readlist"></a>  CRecentFileList::ReadList

최근에 사용 된 레지스트리 또는 응용 프로그램에서 (사용한 MRU) 파일 목록을 읽습니다. INI 파일입니다.

```
virtual void ReadList();
```

##  <a name="remove"></a>  CRecentFileList::Remove

최근에 사용한 파일 목록에서 파일을 제거 합니다.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
가장 최근에 사용한 (MRU) 파일 목록에서 제거할 파일의 0부터 시작 인덱스입니다.

##  <a name="updatemenu"></a>  CRecentFileList::UpdateMenu

최근에 사용한 파일 목록 메뉴 표시를 업데이트합니다.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
에 대 한 포인터를 [CCmdUI](../../mfc/reference/ccmdui-class.md) 가장 최근에 사용한 (MRU) 파일 목록 메뉴에 대 한 개체입니다.

##  <a name="writelist"></a>  CRecentFileList::WriteList

레지스트리 또는 응용 프로그램의 가장 최근에 사용한 (MRU) 파일 목록 씁니다. INI 파일입니다.

```
virtual void WriteList();
```

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)
