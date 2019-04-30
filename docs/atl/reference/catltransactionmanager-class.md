---
title: CAtlTransactionManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: 031d72903d72af77f6929072e4605d32d81585a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260056"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager 클래스

CAtlTransactionManager 클래스 Manager KTM (Kernel Transaction) 함수에 대 한 래퍼를 제공합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlTransactionManager;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[~CAtlTransactionManager](#dtor)|CAtlTransactionManager 소멸자입니다.|
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[닫기](#close)|하나의 트랜잭션 핸들을 닫습니다.|
|[커밋](#commit)|트랜잭션을 커밋할 수를 요청 합니다.|
|[만들기](#create)|트랜잭션 핸들을 만듭니다.|
|[CreateFile](#createfile)|만들거나 파일, 파일 스트림 또는 트랜잭션된 작업 디렉터리를 엽니다.|
|[DeleteFile](#deletefile)|트 랜 잭 트 작업으로 기존 파일을 삭제합니다.|
|[FindFirstFile](#findfirstfile)|트 랜 잭 트 작업으로 파일 또는 하위 디렉터리에 대 한 디렉터리를 검색합니다.|
|[GetFileAttributes](#getfileattributes)|트 랜 잭 트 작업으로 지정 된 파일 또는 디렉터리의 파일 시스템 특성을 검색합니다.|
|[GetFileAttributesEx](#getfileattributesex)|트 랜 잭 트 작업으로 지정 된 파일 또는 디렉터리의 파일 시스템 특성을 검색합니다.|
|[GetHandle](#gethandle)|트랜잭션 핸들을 반환합니다.|
|[IsFallback](#isfallback)|대체 (fallback) 호출 하 여 사용 되는지 여부를 결정 합니다.|
|[MoveFile](#movefile)|기존 파일 또는 해당 자식에 트 랜 잭 트 작업을 포함 하 여 디렉터리를 이동 합니다.|
|[RegCreateKeyEx](#regcreatekeyex)|지정된 된 레지스트리 키를 만들고 트랜잭션과 연결 합니다. 키가 이미 있는 경우 함수도 열립니다.|
|[RegDeleteKey](#regdeletekey)|트 랜 잭 트 작업으로 레지스트리의 지정 된 플랫폼별 뷰에서 하위 키와 해당 값을 삭제합니다.|
|[RegOpenKeyEx](#regopenkeyex)|지정된 된 레지스트리 키를 열고 트랜잭션과 연결 합니다.|
|[롤백](#rollback)|트랜잭션을 롤백할 수 있는 요청 합니다.|
|[SetFileAttributes](#setfileattributes)|트 랜 잭 트 작업으로 파일 또는 디렉터리에 대 한 특성을 설정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|대체 지원 되 면 TRUE입니다. FALSE이 고, 그렇지 합니다.|
|[m_hTransaction](#m_htransaction)|트랜잭션 핸들입니다.|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** atltransactionmanager.h

##  <a name="dtor"></a>  ~CAtlTransactionManager

CAtlTransactionManager 소멸자입니다.

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>설명

정상적인 처리에서 트랜잭션은 자동으로 커밋된 되어 닫힙니다. 를 예외 해제 중 소멸자를 호출 하면 트랜잭션이 롤백 되 고 닫힐 합니다.

##  <a name="catltransactionmanager"></a>  CAtlTransactionManager

CAtlTransactionManager 생성자입니다.

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>매개 변수

*bFallback*<br/>
True 이면 지원 대체 (fallback)를 나타냅니다. 트 랜 잭 트 함수가 실패 한 경우 클래스는 자동으로 "비트랜잭션" 함수를 호출 합니다. FALSE 이면 "대체" 호출 하지 않습니다.

*bAutoCreateTransaction*<br/>
TRUE 이면 트랜잭션 처리기 생성자에 자동으로 만들어집니다. FALSE 되지 않음을 나타냅니다.

### <a name="remarks"></a>설명

##  <a name="close"></a>  닫기

트랜잭션 핸들을 닫습니다.

```
inline BOOL Close();
```

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `CloseHandle` 함수입니다. 메서드는 소멸자에서 자동으로 호출 됩니다.

##  <a name="commit"></a>  Commit

트랜잭션을 커밋할 수를 요청 합니다.

```
inline BOOL Commit();
```

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `CommitTransaction` 함수입니다. 메서드는 소멸자에서 자동으로 호출 됩니다.

##  <a name="create"></a>  만들기

트랜잭션 핸들을 만듭니다.

```
inline BOOL Create();
```

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `CreateTransaction` 함수입니다. 에 대 한 확인

##  <a name="createfile"></a>  CreateFile

만들거나 파일, 파일 스트림 또는 트랜잭션된 작업 디렉터리를 엽니다.

```
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
이름 개체를 만들거나 열 수입니다.

*dwDesiredAccess*<br/>
읽기, 쓰기, 둘 다 또는 둘 (영)으로 요약할 수 있습니다 하는 개체에 대 한 액세스. 가장 일반적으로 사용 되는 값은 GENERIC_READ, GENERIC_WRITE, 또는 둘 다: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*<br/>
공유 모드는 개체 수 읽기, 쓰기, 둘 다를 수, 삭제, 이러한 모든 또는 none입니다. 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.

*lpSecurityAttributes*<br/>
선택적 보안 설명자를 포함 하 고 반환된 된 핸들이 자식 프로세스로 상속 될 수 있는지 여부를 결정 하는 SECURITY_ATTRIBUTES 구조체에 대 한 포인터입니다. 매개 변수는 NULL 일 수 있습니다.

*dwCreationDisposition*<br/>
수행할 동작을 파일에 존재 하 고 존재 하지 않습니다. 이 매개 변수는 함께 사용할 수 없습니다는 다음 값 중 하나 여야 합니다. CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING, 또는 TRUNCATE_EXISTING 합니다.

*dwFlagsAndAttributes*<br/>
파일 특성 및 플래그입니다. 이 매개 변수는 사용 가능한 파일 특성 (FILE_ATTRIBUTE_ *)의 조합을 포함할 수 있습니다. 기타 모든 파일 특성 FILE_ATTRIBUTE_NORMAL를 재정의합니다. 이 매개 변수 플래그의 조합을 포함할 수도 있습니다 (FILE_FLAG_\*)의 버퍼링 동작은 컨트롤에 대 한 액세스 모드 및 기타 특수 플래그입니다. 이러한 모든 FILE_ATTRIBUTE_ 결합할\* 값입니다.

*hTemplateFile*<br/>
유효한 GENERIC_READ 액세스 권한을 사용 하 여 템플릿 파일 핸들입니다. 템플릿 파일을 파일 특성 및 생성 되는 파일에 대 한 확장 된 특성을 제공 합니다. 이 매개 변수는 NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

개체에 액세스할 수 있는 핸들을 반환 합니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `CreateFileTransacted` 함수입니다.

##  <a name="deletefile"></a>  DeleteFile

트 랜 잭 트 작업으로 기존 파일을 삭제합니다.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
삭제할 파일의 이름입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `DeleteFileTransacted` 함수입니다.

##  <a name="findfirstfile"></a>  FindFirstFile

트 랜 잭 트 작업으로 파일 또는 하위 디렉터리에 대 한 디렉터리를 검색합니다.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
디렉터리 또는 경로 및 파일 이름에 대 한 검색입니다. 이 매개 변수는 별표 (*)는 물음표 () 등의 와일드 카드 문자를 포함할 수 있습니다.

*pNextInfo*<br/>
찾은 파일 또는 하위 디렉터리에 대 한 정보를 받는 WIN32_FIND_DATA 구조에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 값은 후속 호출에 사용 된 검색 핸들을 함수에 성공 하면 `FindNextFile` 또는 `FindClose`합니다. 함수 실패 하거나 파일에서 검색 문자열을 찾지 못하면 경우 합니다 *lpFileName* 매개 변수, 반환 값 INVALID_HANDLE_VALUE가 있습니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `FindFirstFileTransacted` 함수입니다.

##  <a name="getfileattributes"></a>  GetFileAttributes

트 랜 잭 트 작업으로 지정 된 파일 또는 디렉터리의 파일 시스템 특성을 검색합니다.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
파일 또는 디렉터리의 이름입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `GetFileAttributesTransacted` 함수입니다.

##  <a name="getfileattributesex"></a>  GetFileAttributesEx

트 랜 잭 트 작업으로 지정 된 파일 또는 디렉터리의 파일 시스템 특성을 검색합니다.

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
파일 또는 디렉터리의 이름입니다.

*fInfoLevelId*<br/>
검색할 특성 정보의 수준입니다.

*lpFileInformation*<br/>
특성 정보를 받는 버퍼에 대 한 포인터입니다. 이 버퍼에 저장 되는 특성 정보 유형의 값에 의해 결정 됩니다 *fInfoLevelId*합니다. 경우는 *fInfoLevelId* 매개 변수는 GetFileExInfoStandard 후이 매개 변수는 WIN32_FILE_ATTRIBUTE_DATA 구조체를 가리킵니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `GetFileAttributesTransacted` 함수입니다.

##  <a name="gethandle"></a>  GetHandle

트랜잭션 핸들을 반환합니다.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>반환 값

클래스에 대 한 트랜잭션 핸들을 반환합니다. NULL을 반환 합니다 `CAtlTransactionManager` 핸들에 연결 되어 있지 않습니다.

### <a name="remarks"></a>설명

##  <a name="isfallback"></a>  IsFallback

대체 (fallback) 호출 하 여 사용 되는지 여부를 결정 합니다.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>반환 값

클래스에서는 대체 (fallback) 호출을 인지 하는 TRUE 반환 합니다. FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

##  <a name="m_bfallback"></a>  m_bFallback

대체 지원 되 면 TRUE입니다. FALSE이 고, 그렇지 합니다.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>설명

##  <a name="m_htransaction"></a>  m_hTransaction

트랜잭션 핸들입니다.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>설명

##  <a name="movefile"></a>  MoveFile

기존 파일 또는 해당 자식에 트 랜 잭 트 작업을 포함 하 여 디렉터리를 이동 합니다.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>매개 변수

*lpOldFileName*<br/>
기존 파일 또는 로컬 컴퓨터의 디렉터리의 현재 이름입니다.

*lpNewFileName*<br/>
파일 또는 디렉터리에 대 한 새 이름입니다. 이 이름이 이미 존재 하지 해야 합니다. 새 파일을 다른 파일 시스템 또는 드라이브 수 있습니다. 새 디렉터리는 동일한 드라이브에 있어야 합니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `MoveFileTransacted` 함수입니다.

##  <a name="regcreatekeyex"></a>  RegCreateKeyEx

지정된 된 레지스트리 키를 만들고 트랜잭션과 연결 합니다. 키가 이미 있는 경우 함수도 열립니다.

```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열고 레지스트리 키에 대 한 핸들입니다.

*lpSubKey*<br/>
이 함수를 열거나 만듭니다는 하위 키의 이름입니다.

*dwReserved*<br/>
이 매개 변수는 예약 되며 0 이어야 합니다.

*lpClass*<br/>
이 키의 사용자 정의 클래스입니다. 이 매개 변수는 무시 될 수 있습니다. 이 매개 변수는 NULL 일 수 있습니다.

*dwOptions*<br/>
이 매개 변수는 다음 값 중 하나일 수 있습니다. REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE, 또는 REG_OPTION_VOLATILE 합니다.

*samDesired*<br/>
키에 대 한 액세스 권한을 지정 하는 마스크입니다.

*lpSecurityAttributes*<br/>
반환된 된 핸들이 자식 프로세스로 상속 될 수 있는지 여부를 결정 하는 SECURITY_ATTRIBUTES 구조체에 대 한 포인터입니다. 하는 경우 *lpSecurityAttributes* 가 null 인 경우 핸들을 상속할 수 없습니다.

*phkResult*<br/>
열린 만들거나 키에 대 한 핸들을 수신 하는 변수에 대 한 포인터입니다. 키를 미리 정의 된 레지스트리 키 중 하나가 아닌 경우 호출을 `RegCloseKey` 핸들 사용을 완료 한 후에 작동 합니다.

*lpdwDisposition*<br/>
다음 disposition 값 중 하나를 수신 하는 변수에 대 한 포인터: REG_CREATED_NEW_KEY 또는 REG_OPENED_EXISTING_KEY 합니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 함수가 실패 한 경우 반환 값은 winerror에 정의 된 0이 아닌 오류 코드입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `RegCreateKeyTransacted` 함수입니다.

##  <a name="regdeletekey"></a>  RegDeleteKey

트 랜 잭 트 작업으로 레지스트리의 지정 된 플랫폼별 뷰에서 하위 키와 해당 값을 삭제합니다.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*hKey*|열고 레지스트리 키에 대 한 핸들입니다.|
|*lpSubKey*|삭제할 키의 이름입니다.|

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 함수가 실패 한 경우 반환 값은 winerror에 정의 된 0이 아닌 오류 코드입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `RegDeleteKeyTransacted` 함수입니다.

##  <a name="regopenkeyex"></a>  RegOpenKeyEx

지정된 된 레지스트리 키를 열고 트랜잭션과 연결 합니다.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열고 레지스트리 키에 대 한 핸들입니다.

*lpSubKey*<br/>
열려는 레지스트리 하위 키의 이름입니다.

*ulOptions*<br/>
이 매개 변수는 예약 되며 0 이어야 합니다.

*samDesired*<br/>
키에 대 한 액세스 권한을 지정 하는 마스크입니다.

*phkResult*<br/>
열린 만들거나 키에 대 한 핸들을 수신 하는 변수에 대 한 포인터입니다. 키를 미리 정의 된 레지스트리 키 중 하나가 아닌 경우 호출을 `RegCloseKey` 핸들 사용을 완료 한 후에 작동 합니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 반환 값은 winerror에 정의 된 0이 아닌 오류 코드는 함수가 실패 한 경우

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `RegOpenKeyTransacted` 함수입니다.

##  <a name="rollback"></a>  Rollback

트랜잭션을 롤백할 수 있는 요청 합니다.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `RollbackTransaction` 함수입니다.

##  <a name="setfileattributes"></a>  SetFileAttributes

트 랜 잭 트 작업으로 파일 또는 디렉터리에 대 한 특성을 설정합니다.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>매개 변수

*lpFileName*<br/>
파일 또는 디렉터리의 이름입니다.

*dwAttributes*<br/>
파일 특성을 파일에 대 한 설정입니다. 자세한 내용은 [SetFileAttributesTransacted](/windows/desktop/api/winbase/nf-winbase-setfileattributestransacteda)합니다.

### <a name="remarks"></a>설명

이 래퍼를 호출 합니다 `SetFileAttributesTransacted` 함수입니다.

## <a name="see-also"></a>참고자료

[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)
