---
title: CDataRecoveryHandler 클래스
ms.date: 03/27/2019
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
ms.openlocfilehash: 5c5836a11dbf9e05db5b56e0bc5c062dd1617b2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253584"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler 클래스

`CDataRecoveryHandler` 자동으로 저장에 설명 하 고 응용 프로그램에서 예기치 않게 종료 되 면 복원 합니다.

## <a name="syntax"></a>구문

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|`CDataRecoveryHandler` 개체를 생성합니다.|

### <a name="methods"></a>메서드

|||
|-|-|
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|각 파일에 등록 하는 자동으로 저장 된 `CDataRecoveryHandler` 클래스입니다.|
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|지정된 된 문서에 자동으로 저장 합니다.|
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|열린 문서 목록에 문서를 추가합니다.|
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|현재 자동 저장 된 파일을 모두 삭제 합니다.|
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|지정한 자동 저장 된 파일을 삭제합니다.|
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|제공 된 문서의 파일 이름과 연결 된 자동 저장 파일 이름을 생성 합니다.|
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|자동 저장 시도 사이의 간격을 반환합니다.|
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|자동 저장 된 파일의 경로 반환합니다.|
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|문서 이름을 검색 한 `CDocument` 개체입니다.|
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|지정된 된 문서에 대 한 일반 제목을 검색합니다.|
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|만들고 복구 된 문서의 제목을 반환 합니다.|
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|응용 프로그램에 대 한 다시 시작 고유 식별자를 검색합니다.|
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|나타냅니다 여부는 `CDataRecoveryHandler` 현재 유휴 상태 루프에는 자동 저장을 수행 합니다.|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|다시 시작 관리자 응용 프로그램이 종료 되도록 발생 하는지 여부를 나타냅니다.|
|[CDataRecoveryHandler::Initialize](#initialize)|`CDataRecoveryHandler`을 초기화합니다.|
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|각 문서에 대 한 사용자에 게 대화 상자를 표시 합니다 `CDataRecoveryHandler` 자동 저장 합니다. 대화 상자 자동 저장 된 문서를 복원 하려면 사용자가 있는지 여부를 결정 합니다.|
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|열린 문서 목록 레지스트리에서 로드합니다.|
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|열린 문서 목록에서 제공된 된 문서를 제거합니다.|
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|이전에 열려 있는 문서를 엽니다.|
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|사용자 입력을 기반으로 자동 저장 된 문서를 복원 합니다.|
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Windows 레지스트리에 현재 열린 문서의 목록을 저장합니다.|
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|밀리초 단위로 자동 주기 사이의 시간을 설정합니다.|
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|자동 저장 된 파일을 저장할 디렉터리를 설정 합니다.|
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|이 인스턴스에 대 한 다시 시작 고유 식별자를 설정 하 여 `CDataRecoveryHandler`입니다.|
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|설정 여부를 `CDataRecoveryHandler` 현재 유휴 주기 동안 열려 있는 문서 정보를 Windows 레지스트리에 저장 합니다.|
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|다시 시작 관리자에서 응용 프로그램의 이전 종료 원인이 있는지 여부를 설정 합니다.|
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|사용자 저장 되므로 문서에 대 한 정보를 업데이트 합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|m_bRestoringPreviousOpenDocs|데이터 복구 처리기가 이전에 열린 문서가 있는지 여부를 나타냅니다.|
|m_bSaveDocumentInfoOnIdle|다음 유휴 루프에서 데이터 복구 처리기 자동으로 저장 설명 하는지 여부를 나타냅니다.|
|m_bShutdownByRestartManager|다시 시작 관리자를 종료 하려면 응용 프로그램이 있는지 여부를 나타냅니다.|
|m_dwRestartManagerSupportFlags|응용 프로그램에 대 한 다시 시작 관리자를 지 원하는 것을 나타내는 플래그를 제공 합니다.|
|m_lstAutosavesToDelete|원래 문서를 닫으면 삭제 되지 않은 자동 저장 된 파일의 목록입니다. 응용 프로그램이 끝날 때 파일을 삭제 하는 다시 시작 관리자 재시도 합니다.|
|m_mapDocNameToAutosaveName|자동 저장 된 파일 이름으로 문서 이름 맵.|
|m_mapDocNameToDocumentPtr|문서 이름으로 이루어진 지도 합니다 [CDocument](../../mfc/reference/cdocument-class.md) 포인터입니다.|
|m_mapDocNameToRestoreBool|자동 저장 된 문서를 복원 여부를 나타내는 부울 매개 변수는 문서 이름 맵.|
|m_mapDocumentPtrToDocName|맵을 여 `CDocument` 문서 이름에 대 한 포인터입니다.|
|m_mapDocumentPtrToDocTitle|맵을 여 `CDocument` 문서 제목에 대 한 포인터입니다. 이러한 제목 파일 저장에 사용 됩니다.|
|m_nAutosaveInterval|자동으로 저장 간격 (밀리초) 시간입니다.|
|m_nTimerID|자동 저장 타이머에 대 한 식별자입니다.|
|m_strAutosavePath|자동 저장 된 문서를 저장할 위치입니다.|
|m_strRestartIdentifier|다시 시작 관리자에 대 한 GUID의 문자열 표현입니다.|

## <a name="remarks"></a>설명

다시 시작 관리자를 사용 하는 `CDataRecoveryHandler` 클래스 유지를 추적 자동 저장 하는 모든 열린 문서의 필요에 따라 합니다. 자동 저장을 사용 하도록 설정 하려면 사용 합니다 [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) 메서드. 이 메서드에 전달 된 `CDataRecoveryHandler` 다음 유휴 루프에는 자동 저장을 수행 하 합니다. 다시 시작 관리자 호출 `SetSaveDocumentInfoOnIdle` 경우는 `CDataRecoveryHandler` 자동 저장을 수행 해야 합니다.

모든 메서드는 `CDataRecoveryHandler` 클래스는 가상입니다. 사용자 고유의 사용자 지정 데이터 복구 처리기를 만들려면이 클래스의 메서드를 재정의 합니다. 사용자 고유의 데이터 복구 처리기를 만들거나 관리자 다시 시작 하지 않는 한 CDataRecoveryHandler를 인스턴스화할 수 없습니다. 합니다 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md) 만듭니다는 `CDataRecoveryHandler` 필요 하므로 개체입니다.

사용 하기 전에 `CDataRecoveryHandler` 개체를 호출 해야 합니다 [CDataRecoveryHandler::Initialize](#initialize)합니다.

때문에 합니다 `CDataRecoveryHandler` 클래스를 다시 시작 관리자 밀접 하 게 연결할 `CDataRecoveryHandler` 전역 매개 변수에 따라 달라 집니다 `m_dwRestartManagerSupportFlags`합니다. 이 매개 변수는 다시 시작 관리자에 어떤 사용 권한 및 응용 프로그램과 함께 작용 하는 방법을 결정 합니다. 기존 응용 프로그램으로 다시 시작 관리자에 통합 하려면 할당 해야 `m_dwRestartManagerSupportFlags` 주 응용 프로그램의 생성자에서 적절 한 값입니다. 다시 시작 관리자를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** afxdatarecovery.h

##  <a name="autosavealldocumentinfo"></a>  CDataRecoveryHandler::AutosaveAllDocumentInfo

각 파일에 등록 하는 자동으로 저장 된 `CDataRecoveryHandler` 클래스입니다.

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>반환 값

True는 `CDataRecoveryHandler` 모든 문서를 저장 합니다. FALSE 이면 모든 문서 저장 되지 않았습니다.

### <a name="remarks"></a>설명

이 메서드를 저장 해야 하는 문서가 없는 경우 TRUE를 반환 합니다. 또한 검색 하는 경우 모든 문서를 저장 하지 않고 TRUE를 반환 합니다 `CWinApp` 또는 `CDocManager` 오류를 생성 하는 응용 프로그램에 대 한 합니다.

이 메서드를 사용 하려면 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 또는 AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL 설정 해야 `m_dwRestartManagerSupportFlags`합니다. 자세한 내용은 [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)를 참조하세요.

##  <a name="autosavedocumentinfo"></a>  CDataRecoveryHandler::AutosaveDocumentInfo

지정된 된 문서에 자동으로 저장 합니다.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDocument*|[in] 에 대 한 포인터를 `CDocument` 저장 합니다.|
|*bResetModifiedFlag*|[in] TRUE 이면 합니다 `CDataRecoveryHandler` 고려 *pDocument* 수정할; FALSE 이면 프레임 워크에서는 간주 한다는 *pDocument* 되도록 수정 합니다. 이 플래그의 효과 대 한 자세한 내용은 설명 섹션을 참조 하세요.|

### <a name="return-value"></a>반환 값

적절 한 플래그 설정 된 경우 TRUE이 고 *pDocument* 유효한 `CDocument` 개체입니다.

### <a name="remarks"></a>설명

각 `CDocument` 개체에 마지막으로 저장 한 이후 변경 되었는지 여부를 나타내는 플래그입니다. 사용 하 여 [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) 이 플래그의 상태를 결정 합니다. 경우는 `CDocument` 마지막 저장 이후 변경 되지 않은 `AutosaveDocumentInfo` 해당 문서에 대 한 모든 자동 저장 된 파일을 삭제 합니다. 문서 마지막 저장 이후 변경 된 경우 닫기 사용자 닫기 전에 문서를 저장 하 라는 메시지가 표시 됩니다.

> [!NOTE]
>  사용 하 여 *bResetModifiedFlag* 수정 되지 않은 문서의 상태 변경에 저장 되지 않은 데이터 손실 발생할 수 있습니다. 프레임 워크에서 수정 되지 않은 문서를 닫거나 표시 하지 않습니다 저장할 사용자.

이 방법을 사용 하 여 예외를 throw 합니다 [ASSERT](diagnostic-services.md#assert) 매크로 경우 *pDocument* 올바르지 않습니다 `CDocument` 개체입니다.

이 메서드를 사용 하려면 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 또는 AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL 해야에서 설정할 *m_dwRestartManagerSupportFlags*합니다.

##  <a name="cdatarecoveryhandler"></a>  CDataRecoveryHandler::CDataRecoveryHandler

`CDataRecoveryHandler` 개체를 생성합니다.

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*dwRestartManagerSupportFlags*|[in] 지원 되는 다시 시작 관리자의 어떤 옵션을 나타냅니다.|
|*nAutosaveInterval*|[in] 자동으로 저장 사이의 시간입니다. 이 매개 변수는 밀리초에서입니다.|

### <a name="remarks"></a>설명

MFC 프레임 워크에서 자동으로 만듭니다는 `CDataRecoveryHandler` 사용 하는 경우 응용 프로그램에 대 한 개체를 **새 프로젝트** 마법사. 데이터 복구 동작 또는 다시 시작 관리자를 사용자 지정 하려는 경우가 아니면 만들면 안을 `CDataRecoveryHandler` 개체입니다.

##  <a name="createdocumentinfo"></a>  CDataRecoveryHandler::CreateDocumentInfo

열린 문서 목록에 문서를 추가합니다.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDocument*|[in] 에 대 한 포인터를 `CDocument`입니다. 이 메서드는이 문서의 정보를 만듭니다 `CDocument`합니다.|

### <a name="return-value"></a>반환 값

기본 구현에서는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 경우 확인 *pDocument* 문서를 추가 하기 전에 문서 목록에 이미 있습니다. 하는 경우 *pDocument* 이미이 메서드는 목록에서 사용 하 여 연결 된 자동 저장 된 파일 삭제 *pDocument*합니다.

이 메서드를 사용 하려면 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 또는 AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL 해야에서 설정할 *m_dwRestartManagerSupportFlags*합니다.

##  <a name="deleteallautosavedfiles"></a>  CDataRecoveryHandler::DeleteAllAutosavedFiles

현재 자동 저장 된 파일을 모두 삭제 합니다.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다.

##  <a name="deleteautosavedfile"></a>  CDataRecoveryHandler::DeleteAutosavedFile

지정한 자동 저장 된 파일을 삭제합니다.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*strAutosavedFile*|[in] 자동 저장 된 파일 이름을 포함 하는 문자열입니다.|

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 자동 저장 된 파일을 삭제할 수 없는 경우 목록의 파일의 이름을 저장 합니다. 에 대 한 소멸자는 `CDataRecoveryHandler` 해당 목록에 지정 된 각 자동 저장 된 파일을 삭제 하려고 합니다.

##  <a name="generateautosavefilename"></a>  CDataRecoveryHandler::GenerateAutosaveFileName

제공 된 문서의 파일 이름과 연결 된 자동 저장 파일 이름을 생성 합니다.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>매개 변수

*strDocumentName*<br/>
[in] 문서 이름을 포함 하는 문자열입니다. `GenerateAutosaveFileName` 이 문서 이름을 사용 하 여 해당 자동 저장 파일 이름을 생성 합니다.

### <a name="return-value"></a>반환 값

생성 된 자동 저장 파일 이름을 *strDocumentName*합니다.

### <a name="remarks"></a>설명

각 문서 이름에 자동 저장 파일 이름으로 한 일 매핑이 있습니다.

##  <a name="getautosaveinterval"></a>  CDataRecoveryHandler::GetAutosaveInterval

자동 저장 시도 사이의 간격을 반환합니다.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>반환 값

자동 저장 간격 (밀리초)의 수를 가져오려고 시도합니다.

##  <a name="getautosavepath"></a>  CDataRecoveryHandler::GetAutosavePath

자동 저장 된 파일의 경로 반환합니다.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>반환 값

자동 저장 된 문서를 저장할 위치입니다.

##  <a name="getdocumentlistname"></a>  CDataRecoveryHandler::GetDocumentListName

문서 이름을 검색 한 `CDocument` 개체입니다.

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDocument*|[in] 에 대 한 포인터를 `CDocument`입니다. `GetDocumentListName` 이 문서 이름을 검색 `CDocument`합니다.|

### <a name="return-value"></a>반환 값

문서 이름 *pDocument*합니다.

### <a name="remarks"></a>설명

합니다 `CDataRecoveryHandler` 문서 이름을 키로 사용 하 여 *m_mapDocNameToAutosaveName*를 *m_mapDocNameToDocumentPtr*, 및 *m_mapDocNameToRestoreBool*합니다. 이러한 매개 변수를 사용 하도록 설정 합니다 `CDataRecoveryHandler` 모니터링할 `CDocument` 개체, 자동 저장 파일 이름 및 자동 저장 설정 합니다.

##  <a name="getnormaldocumenttitle"></a>  CDataRecoveryHandler::GetNormalDocumentTitle

지정된 된 문서에 대 한 일반 제목을 검색합니다.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDocument*|[in] 에 대 한 포인터를 `CDocument`입니다.|

### <a name="return-value"></a>반환 값

지정된 된 문서에 대 한 일반 제목입니다.

### <a name="remarks"></a>설명

일반 문서 제목은 일반적으로 경로 없이 문서의 파일 이름입니다. 제목에 **파일 이름** 필드를 **다른 이름으로 저장** 대화 상자.

##  <a name="getrecovereddocumenttitle"></a>  CDataRecoveryHandler::GetRecoveredDocumentTitle

만들고 복구 된 문서의 제목을 반환 합니다.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>매개 변수

*strDocumentTitle*<br/>
[in] 일반적인 제목 문서입니다.

### <a name="return-value"></a>반환 값

복구 된 문서 제목입니다.

### <a name="remarks"></a>설명

기본적으로 복구 된 문서 제목은 일반 제목을 **[복구 됨]** 추가 합니다. 복구 된 제목은 사용자에 게 표시 됩니다 때는 `CDataRecoveryHandler` 자동 저장 된 문서를 복원 하려면 사용자를 쿼리 합니다.

##  <a name="getrestartidentifier"></a>  CDataRecoveryHandler::GetRestartIdentifier

응용 프로그램에 대 한 다시 시작 고유 식별자를 검색합니다.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>반환 값

고유 식별자를 다시 시작합니다.

### <a name="remarks"></a>설명

다시 시작 식별자는 응용 프로그램의 각 실행에 대해 고유 합니다.

`CDataRecoveryHandler` 현재 열려 있는 문서에 대 한 레지스트리 정보를 저장 합니다. 다시 시작 식별자를 응용 프로그램을 종료 하 고 다시 시작 하는 다시 시작 관리자를 할 때 제공 된 `CDataRecoveryHandler`합니다. `CDataRecoveryHandler` 다시 식별자를 사용 하 여 이전에 열린 문서의 목록을 검색 합니다. 그러면는 `CDataRecoveryHandler` 찾기 및 자동 저장 된 파일을 복원 하려고 합니다.

##  <a name="getsavedocumentinfoonidle"></a>  CDataRecoveryHandler::GetSaveDocumentInfoOnIdle

나타냅니다 여부는 `CDataRecoveryHandler` 현재 유휴 상태 루프에는 자동 저장을 수행 합니다.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>반환 값

True는 `CDataRecoveryHandler` 현재 유휴 상태 루프에 자동으로 저장 FALSE 하지 않는 것을 나타냅니다.

##  <a name="getshutdownbyrestartmanager"></a>  CDataRecoveryHandler::GetShutdownByRestartManager

다시 시작 관리자 응용 프로그램이 종료 되도록 발생 하는지 여부를 나타냅니다.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 인해 종료; 응용 프로그램이 다시 시작 관리자 FALSE 이면 지원 되지 않았습니다.

##  <a name="initialize"></a>  CDataRecoveryHandler::Initialize

`CDataRecoveryHandler`을 초기화합니다.

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>반환 값

초기화에 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

초기화 프로세스는 레지스트리에서 자동 저장 파일을 저장 하는 것에 대 한 경로 로드 합니다. 경우는 `Initialize` 메서드는이 디렉터리를 찾을 수 없거나 또는 경로가 NULL 인 경우 `Initialize` 실패 하 고 반환 `FALSE`합니다.

사용 하 여 [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) 응용 프로그램 초기화 한 후 자동 저장 경로 변경 하 여 `CDataRecoveryHandler`합니다.

`Initialize` 메서드는 또한 다음 자동 저장을 수행 하는 때를 모니터링 합니다. 타이머를 시작 합니다. 사용 하 여 [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) 응용 프로그램 초기화 한 후 자동 저장 간격을 변경 하려면를 `CDataRecoveryHandler`입니다.

##  <a name="queryrestoreautosaveddocuments"></a>  CDataRecoveryHandler::QueryRestoreAutosavedDocuments

각 문서에 대 한 사용자에 게 대화 상자를 표시 합니다 `CDataRecoveryHandler` 자동 저장 합니다. 대화 상자 자동 저장 된 문서를 복원 하려면 사용자가 있는지 여부를 결정 합니다.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>설명

이 메서드를 표시 하는 유니코드 응용 프로그램을 사용 하는 경우는 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) 사용자에 게 합니다. 프레임 워크를 사용 하 여이 고, 그렇지 [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) 사용자를 쿼리할 수 있습니다.

이후에 `QueryRestoreAutosavedDocuments` 모든 응답을 수집 사용자 로부터 정보를 저장 합니다 멤버 변수의 *m_mapDocNameToRestoreBool*합니다. 이 메서드는 자동 저장 된 문서를 복원 하지 않습니다.

##  <a name="readopendocumentlist"></a>  CDataRecoveryHandler::ReadOpenDocumentList

열린 문서 목록 레지스트리에서 로드합니다.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>반환 값

TRUE 이면는 `ReadOpenDocumentList` 레지스트리;에서 하나 이상의 문서에 대 한 정보를 로드 FALSE 이면 로드 된 문서 정보가 없습니다.

### <a name="remarks"></a>설명

이 함수는 레지스트리에서 열려 있는 문서 정보를 로드 하 고 멤버 변수에 저장 *m_mapDocNameToAutosaveName*합니다.

후 `ReadOpenDocumentList` 모든 데이터를 로드 레지스트리에서 문서 정보를 삭제 합니다.

##  <a name="removedocumentinfo"></a>  CDataRecoveryHandler::RemoveDocumentInfo

열린 문서 목록에서 제공된 된 문서를 제거합니다.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDocument*|[in] 제거할 문서에 대 한 포인터입니다.|

### <a name="return-value"></a>반환 값

TRUE 이면 *pDocument* 목록에서 제거 되었습니다 FALSE 이면 오류가 발생 했습니다.

### <a name="remarks"></a>설명

사용자가 문서를 닫으면 프레임 워크 열린 문서 목록에서 제거 하려면이 메서드를 사용 합니다.

하는 경우 `RemoveDocumentInfo` 찾을 수 없습니다 *pDocument* 열린 문서 목록에서 아무 작업도 수행 하지 하 고 TRUE를 반환 합니다.

이 메서드를 사용 하려면 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES에서 설정 해야 합니다 *m_dwRestartManagerSupportFlags*합니다.

##  <a name="reopenpreviousdocuments"></a>  CDataRecoveryHandler::ReopenPreviousDocuments

이전에 열려 있는 문서를 엽니다.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>반환 값

하나 이상의 문서를 열었을 때; TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 이전에 열려 있는 문서의 가장 최근 저장을 엽니다. 문서 저장 되지 않았습니다 하는 경우 또는 자동 저장, `ReopenPreviousDocuments` 해당 파일 형식에 대 한 템플릿을 기반으로 하는 빈 문서를 엽니다.

이 메서드를 사용 하려면 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES에서 설정 해야 합니다 *m_dwRestartManagerSupportFlags*합니다. 이 매개 변수를 설정 하지 않으면 `ReopenPreviousDocuments` 없으며 FALSE를 반환 합니다.

이전에 열린 문서의 목록을 저장 된 문서가 없는 경우 `ReopenPreviousDocuments` 없으며 FALSE를 반환 합니다.

##  <a name="restoreautosaveddocuments"></a>  CDataRecoveryHandler::RestoreAutosavedDocuments

사용자 입력을 기반으로 자동 저장 된 문서를 복원 합니다.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>반환 값

이 메서드는 문서를 성공적으로 복원 하는 경우 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) 복원 하려고 설명 하 고 사용자를 확인 합니다. 사용자가 자동 저장 된 문서를 복원 하지 `RestoreAutosavedDocuments` 자동 저장 파일을 삭제 합니다. 그렇지 않으면 `RestoreAutosavedDocuments` 열린 문서가 자동 저장 된 버전으로 바꿉니다.

이 메서드를 사용 하려면 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES 또는 AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES 설정 해야 `m_dwRestartManagerSupportFlags`합니다.

##  <a name="saveopendocumentlist"></a>  CDataRecoveryHandler::SaveOpenDocumentList

Windows 레지스트리에 현재 열린 문서의 목록을 저장합니다.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>반환 값

성공적으로 저장 된 경우 나 저장할 열린 문서가 없는 경우 TRUE입니다. 레지스트리에 저장 하는 문서가 있지만 오류가 발생 했기 때문에 저장 하지 않은 경우 FALSE입니다.

### <a name="remarks"></a>설명

다시 시작 관리자 호출 `SaveOpenDocumentList` 응용 프로그램이 예기치 않게 종료 하는 경우 또는 업그레이드에 대 한 종료 되는 경우. 사용 하 여 응용 프로그램을 다시 시작 되 면 [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) 열려 있는 문서의 목록을 검색 합니다.

이 메서드는 열려 있는 문서의 목록만 저장합니다. 메서드 [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) 은 문서 자체를 저장 해야 합니다.

##  <a name="setautosaveinterval"></a>  CDataRecoveryHandler::SetAutosaveInterval

밀리초 단위로 자동 주기 사이의 시간을 설정합니다.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>매개 변수

*nAutosaveInterval*<br/>
[in] 시간 (밀리초)는 새 자동 저장 간격입니다.

##  <a name="setautosavepath"></a>  CDataRecoveryHandler::SetAutosavePath

자동 저장 된 파일을 저장할 디렉터리를 설정 합니다.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*strAutosavePath*|[in] 자동 저장 파일을 저장할 경로입니다.|

### <a name="remarks"></a>설명

자동 저장 디렉터리를 변경 합니다. 움직이지 않으면 현재 자동 저장 된 파일입니다.

##  <a name="setrestartidentifier"></a>  CDataRecoveryHandler::SetRestartIdentifier

이 인스턴스에 대 한 다시 시작 고유 식별자를 설정 하 여 `CDataRecoveryHandler`입니다.

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*strRestartIdentifier*|[in] 다시 시작 관리자에 대 한 고유 식별자입니다.|

### <a name="remarks"></a>설명

다시 시작 관리자는 레지스트리에서 열려 있는 문서에 대 한 정보를 기록합니다. 이 정보는 키로 다시 시작 고유 식별자를 사용 하 여 저장 됩니다. 다시 시작 식별자가 응용 프로그램의 각 인스턴스에 대해 고유 하므로 응용 프로그램의 여러 인스턴스 예기치 않게 종료 될 수 있습니다 하 고 다시 시작 관리자는 각각의 복구할 수 있습니다.

##  <a name="setsavedocumentinfoonidle"></a>  CDataRecoveryHandler::SetSaveDocumentInfoOnIdle

설정 여부를 `CDataRecoveryHandler` 현재 유휴 주기 동안 열려 있는 문서 정보를 Windows 레지스트리에 저장 합니다.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*bSaveOnIdle*|[in] 현재 유휴 주기; 동안 문서 정보를 저장. False 이면 저장을 수행 하지 않습니다.|

##  <a name="setshutdownbyrestartmanager"></a>  CDataRecoveryHandler::SetShutdownByRestartManager

다시 시작 관리자에서 응용 프로그램의 이전 종료 원인이 있는지 여부를 설정 합니다.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*bShutdownByRestartManager*|[in] 다시 시작 관리자는 응용 프로그램을 종료; 발생 한다는 것을 나타내려면 False 이면 다른 이유로 응용 프로그램이 종료 되었음을 나타냅니다.|

### <a name="remarks"></a>설명

프레임 워크는 이전 종료 예기치 않은 여부 또는 다시 시작 관리자가 초기화 되었는지 여부에 따라 다르게 동작 합니다.

##  <a name="updatedocumentinfo"></a>  CDataRecoveryHandler::UpdateDocumentInfo

사용자 저장 되므로 문서에 대 한 정보를 업데이트 합니다.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDocument*|[in] 저장된 된 문서에 대 한 포인터입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 자동 저장 된 문서를 삭제 하 고 문서 정보를 업데이트 하는 경우 TRUE입니다. FALSE 이면 오류가 발생 했습니다.

### <a name="remarks"></a>설명

사용자가 문서를 저장 하는 경우 더 이상 필요 하므로 응용 프로그램 자동 저장 된 파일을 제거 합니다. `UpdateDocumentInfo` 호출 하 여 자동 저장 된 파일을 삭제 [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)합니다. `UpdateDocumentInfo` 다음의 정보를 추가 *pDocument* 오픈 설명 하므로 현재 목록을 `RemoveDocumentInfo` 해당 정보를 하지만 저장 된 삭제 문서가 열려 합니다.

이 메서드를 사용 하려면 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES에서 설정 해야 합니다 *m_dwRestartManagerSupportFlags*합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)
