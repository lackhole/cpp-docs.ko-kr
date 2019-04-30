---
title: CFile 클래스
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: db499ffa5f1d82b6e3622287f86132930a929102
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385312"
---
# <a name="cfile-class"></a>CFile 클래스

MFC 파일 클래스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CFile : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFile::CFile](#cfile)|생성 된 `CFile` 경로 또는 파일 핸들에서 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFile::Abort](#abort)|모든 경고 및 오류를 무시 하는 파일을 닫습니다.|
|[CFile::Close](#close)|파일을 닫고 개체를 삭제 합니다.|
|[CFile::Duplicate](#duplicate)|이 파일을 기반으로 중복 개체를 생성 합니다.|
|[CFile::Flush](#flush)|아직 쓸 데이터를 플러시합니다.|
|[CFile::GetFileName](#getfilename)|선택한 파일의 파일 이름을 검색합니다.|
|[CFile::GetFilePath](#getfilepath)|선택한 파일의 전체 파일 경로 검색합니다.|
|[CFile::GetFileTitle](#getfiletitle)|선택한 파일의 제목을 검색합니다.|
|[CFile::GetLength](#getlength)|파일의 길이 검색합니다.|
|[CFile::GetPosition](#getposition)|현재 파일 포인터를 검색합니다.|
|[CFile::GetStatus](#getstatus)|정적 버전 또는 열려 있는 파일의 상태를 검색, 지정된 된 파일 (정적이 고 가상 함수)의 상태를 검색 합니다.|
|[CFile::LockRange](#lockrange)|파일의 바이트 범위를 잠급니다.|
|[CFile::Open](#open)|안전 하 게 오류 테스트 옵션을 사용 하 여 파일을 엽니다.|
|[CFile::Read](#read)|현재 파일 위치에 있는 파일에서 (버퍼링 되지 않은) 데이터를 읽기입니다.|
|[CFile::Remove](#remove)|지정된 된 파일 (정적 함수)를 삭제합니다.|
|[CFile::Rename](#rename)|지정된 된 파일을 (정적 함수)의 이름을 바꿉니다.|
|[CFile::Seek](#seek)|현재 파일 포인터를 배치합니다.|
|[CFile::SeekToBegin](#seektobegin)|파일의 시작 부분에는 현재 파일 포인터를 배치합니다.|
|[CFile::SeekToEnd](#seektoend)|파일의 끝에 있는 현재 파일 포인터를 배치합니다.|
|[CFile::SetFilePath](#setfilepath)|선택한 파일의 전체 파일 경로 설정합니다.|
|[CFile::SetLength](#setlength)|파일의 길이 변경합니다.|
|[CFile::SetStatus](#setstatus)|지정된 된 파일 (정적이 고 가상 함수)의 상태를 설정합니다.|
|[CFile::UnlockRange](#unlockrange)|파일의 바이트 범위 잠금을 해제합니다.|
|[CFile::Write](#write)|현재 파일 위치에 파일에 (버퍼링 되지 않은) 데이터를 씁니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CFile::operator HANDLE](#operator_handle)|에 대 한 핸들을 `CFile` 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFile::hFileNull](#hfilenull)|있는지 여부를 확인 합니다 `CFile` 개체에 대 한 유효한 핸들입니다.|
|[CFile::m_hFile](#m_hfile)|일반적으로 운영 체제 파일 핸들을 포함합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFile::m_pTM](#m_ptm)|에 대 한 포인터 `CAtlTransactionManager` 개체입니다.|

## <a name="remarks"></a>설명

버퍼링 되지 않은 이진 디스크 입출력 서비스를 직접 제공 하 고 직접 지원 하지 해당 파생된 클래스를 통해 메모리 파일 및 텍스트 파일입니다. `CFile` 와 함께 작동 합니다 `CArchive` 클래스 Microsoft Foundation Class 개체의 serialization을 지원 합니다.

이 클래스와 파생된 클래스 간의 계층 관계 인스턴스는 다형성을 통해 모든 파일 개체에 대해 작동 하도록 프로그램을 사용 하면 `CFile` 인터페이스입니다. 예를 들어, 메모리 파일을 디스크 파일은 작동합니다.

사용 하 여 `CFile` 및 범용 디스크 I/O에 대 한 파생된 클래스입니다. 사용 하 여 `ofstream` 또는 디스크 파일을 전송 하는 서식 있는 텍스트에 대 한 다른 Microsoft iostream 클래스입니다.

일반적으로 디스크 파일을 열에 자동으로 `CFile` 생성과 소멸에 종결된 합니다. 정적 멤버 함수를 허용 하 파일을 열지 않고 파일의 상태를 검색할 수 있습니다.

사용 하 여 대 한 자세한 내용은 `CFile`, 문서를 참조 하세요 [MFC의 파일](../../mfc/files-in-mfc.md) 하 고 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="abort"></a>  CFile::Abort

이 개체와 연결 된 파일을 닫고 파일을 읽거나 쓰기 위해 사용할 수 없게 하 게 합니다.

```
virtual void Abort();
```

### <a name="remarks"></a>설명

개체를 소멸 하기 전에 파일을 닫지 않은 경우 소멸자를 닫습니다.

예외를 처리 하는 경우 `CFile::Abort` 에서 다른 `CFile::Close` 중요 한 두 가지가 있습니다. 먼저 합니다 `Abort` 함수는 예외를 throw 하지 오류에에서 오류를 무시 하므로 `Abort`합니다. 두 번째로 `Abort` 것입니다 **ASSERT** 파일이 아직 열려 있지 않거나 이전에 종료 되었습니다.

사용 하는 경우 **새** 할당할는 `CFile` 힙에 개체 파일을 닫은 후 삭제 해야 합니다. `Abort` 설정 `m_hFile` 에 `CFile::hFileNull`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

##  <a name="cfile"></a>  CFile::CFile

`CFile` 개체를 생성하고 초기화합니다.

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
`CFile` 개체에 연결할 파일의 핸들입니다.

*lpszFileName*<br/>
`CFile` 개체에 연결할 파일의 상대 또는 전체 경로입니다.

*nOpenFlags*<br/>
지정한 파일에 대한 파일 액세스 옵션의 비트 조합(OR)입니다. 사용 가능한 옵션은 설명 섹션을 참조하세요.

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

다음 5 개 테이블에 대 한 가능한 옵션을 나열 합니다 *nOpenFlags* 매개 변수입니다.

다음 파일 액세스 모드 옵션 중 하나만 선택해야 합니다. 기본 파일 액세스 모드는 `CFile::modeRead`(읽기 전용)입니다.

|값|설명|
|-----------|-----------------|
|`CFile::modeRead`|읽기 권한만 요청합니다.|
|`CFile::modeWrite`|쓰기 권한만 요청합니다.|
|`CFile::modeReadWrite`|읽기 및 쓰기 권한을 요청합니다.|

다음 문자 모드 옵션 중 하나를 선택합니다.

|값|설명|
|-----------|-----------------|
|`CFile::typeBinary`|이진 모드를 설정합니다(파생 클래스에만 사용됨).|
|`CFile::typeText`|캐리지 리턴-줄 바꿈 쌍 (파생된 클래스에만 사용)에 대 한 특수 처리를 사용 하 여 텍스트 모드를 설정 합니다.|
|`CFile::typeUnicode`|유니코드 모드를 설정합니다(파생 클래스에만 사용됨). 응용 프로그램을 유니코드 구성에서 빌드할 때는 텍스트가 유니코드 형식으로 파일에 기록됩니다. BOM이 파일에 기록되지 않습니다.|

다음 파일 공유 모드 옵션 중 하나만 선택해야 합니다. 기본 파일 공유 모드는 `CFile::shareExclusive`(단독)입니다.

|값|설명|
|-----------|-----------------|
|`CFile::shareDenyNone`|공유 제한이 없습니다.|
|`CFile::shareDenyRead`|다른 모든 사용자에 대해 읽기 권한을 거부합니다.|
|`CFile::shareDenyWrite`|다른 모든 사용자에 대해 쓰기 권한을 거부합니다.|
|`CFile::shareExclusive`|다른 모든 사용자에 대해 읽기 및 쓰기 권한을 거부합니다.|

다음 파일 만들기 모드 옵션 중 첫 번째 옵션 또는 두 옵션을 모두 선택합니다. 기본 만들기 모드는 `CFile::modeNoTruncate`(기존 파일 열기)입니다.

|값|설명|
|-----------|-----------------|
|`CFile::modeCreate`|파일이 없으면 새 파일을 만듭니다. 파일이 이미 있는 경우 덮어쓸 이므로 처음에 길이가 0으로 설정 합니다.|
|`CFile::modeNoTruncate`|파일이 없으면 새 파일을 만듭니다. 파일이 이미 있으면 `CFile` 개체에 연결됩니다.|

설명에 따라 다음 파일 캐싱 옵션을 선택합니다. 기본적으로 시스템은 옵션으로 제공되지 않는 범용 캐싱 구성표를 사용합니다.

|값|설명|
|-----------|-----------------|
|`CFile::osNoBuffer`|시스템에서 파일에 대해 중간 캐시를 사용하지 않습니다. 이 옵션은 다음 2개 옵션을 취소합니다.|
|`CFile::osRandomAccess`|임의 액세스를 위해 파일 캐시가 최적화됩니다. 이 옵션과 순차 검색 옵션을 함께 사용해서는 안 됩니다.|
|`CFile::osSequentialScan`|순차 액세스를 위해 파일 캐시가 최적화됩니다. 이 옵션과 임의 액세스 옵션을 함께 사용해서는 안 됩니다.|
|`CFile::osWriteThrough`|쓰기 작업이 지연 없이 수행됩니다.|

파일 핸들이 상속되지 않도록 하려면 다음 보안 옵션을 선택합니다. 기본적으로 새 자식 프로세스는 파일 핸들을 사용할 수 있습니다.

|값|설명|
|-----------|-----------------|
|`CFile::modeNoInherit`|자식 프로세스가 파일 핸들을 사용하지 못하도록 차단합니다.|

기본 생성자는 멤버를 초기화하지만 파일을 `CFile` 개체에 연결하지는 않습니다. 이 생성자를 사용한 후 사용 합니다 [CFile::Open](#open) 파일을 열에 연결 하는 메서드를 `CFile` 개체입니다.

매개 변수가 하나 포함된 생성자는 멤버를 초기화하고 기존 파일을 `CFile` 개체에 연결합니다.

매개 변수가 두 개 포함된 생성자는 멤버를 초기화하고 지정한 파일 열기를 시도합니다. 이 생성자가 지정한 파일을 정상적으로 열면 파일은 `CFile` 개체에 연결되고, 그렇지 않으면 이 생성자가 `CInvalidArgException` 개체에 대한 포인터를 throw합니다. 예외를 처리 하는 방법에 대 한 자세한 내용은 참조 하세요. [예외](../../mfc/exception-handling-in-mfc.md)합니다.

`CFile` 개체가 지정한 파일을 정상적으로 열면 `CFile` 개체 제거 시 이 파일이 자동으로 닫힙니다. 그렇지 않으면 `CFile` 개체에서 파일 연결을 끊은 후 파일을 명시적으로 닫아야 합니다.

### <a name="example"></a>예제

다음 코드에서는 `CFile` 사용 방법을 보여줍니다.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

##  <a name="close"></a>  CFile::Close

이 개체와 연결 된 파일을 닫고 파일을 읽거나 쓰기 위해 사용할 수 없게 하 게 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

개체를 소멸 하기 전에 파일을 닫지 않은 경우 소멸자를 닫습니다.

사용 하는 경우 **새** 할당할는 `CFile` 힙에 개체 파일을 닫은 후 삭제 해야 합니다. `Close` 설정 `m_hFile` 에 `CFile::hFileNull`입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CFile::CFile](#cfile)합니다.

##  <a name="duplicate"></a>  CFile::Duplicate

중복 생성 `CFile` 지정된 된 파일에 대 한 개체입니다.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>반환 값

중복에 대 한 포인터 `CFile` 개체입니다.

### <a name="remarks"></a>설명

이 C 런타임 함수에 해당 하는 `_dup`합니다.

##  <a name="flush"></a>  CFile::Flush

파일에 쓸 파일 버퍼에 남아 있는 데이터를 강제로 수행 합니다.

```
virtual void Flush();
```

### <a name="remarks"></a>설명

사용 `Flush` 플러시하도록를 보장 하지는 않습니다 `CArchive` 버퍼입니다. 보관을 사용 하는 경우 호출 [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) 첫 번째입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CFile::SetFilePath](#setfilepath)합니다.

##  <a name="getfilename"></a>  CFile::GetFileName

지정된 된 파일의 이름을 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>반환 값

파일의 이름입니다.

### <a name="remarks"></a>설명

예를 들어, 호출 하는 경우 `GetFileName` 파일에 대 한 사용자에 게 메시지를 생성할 `c:\windows\write\myfile.wri`, 파일 이름, `myfile.wri`, 반환 됩니다.

이름을 포함 하는 파일의 전체 경로 반환 하려면 호출 [GetFilePath](#getfilepath)합니다. 파일의 제목에 반환할 ( `myfile`), 호출 [GetFileTitle](#getfiletitle)합니다.

### <a name="example"></a>예제

이 코드 조각은 시스템을 엽니다. WINDOWS 디렉터리에서 INI 파일입니다. 하는 경우, 예제 출력 됩니다 이름 및 경로, 제목, 출력에 표시 된 대로:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

##  <a name="getfilepath"></a>  CFile::GetFilePath

지정된 된 파일의 전체 경로 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>반환 값

지정된 된 파일의 전체 경로입니다.

### <a name="remarks"></a>설명

예를 들어, 호출 하는 경우 `GetFilePath` 파일에 대 한 사용자에 게 메시지를 생성할 `c:\windows\write\myfile.wri`, 파일 경로 `c:\windows\write\myfile.wri`에 반환 됩니다.

파일의 이름을 반환할 (`myfile.wri`), 호출 [GetFileName](#getfilename)합니다. 파일의 제목에 반환할 (`myfile`), 호출 [GetFileTitle](#getfiletitle)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetFileName](#getfilename)합니다.

##  <a name="getfiletitle"></a>  CFile::GetFileTitle

파일에 대 한 파일 제목 (표시 이름)을 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>반환 값

기본 파일의 제목입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) 검색할 파일의 제목입니다. 성공 하면 메서드는 시스템 사용자에 게 파일 이름을 표시 하는 데 사용할 문자열을 반환 합니다. 메서드를 호출 하는 고, 그렇지 [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) 를 기본 파일의 파일 이름 (파일 확장명 포함)를 검색 합니다. 따라서 파일 확장명은 항상 수에 포함 되지 반환 되는 파일 제목 문자열. 자세한 내용은 [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) 하 고 [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) Windows SDK의 합니다.

이름을 포함 하는 파일의 전체 경로 반환 하려면 호출 [GetFilePath](#getfilepath)합니다. 파일의 이름을 반환할 호출 [GetFileName](#getfilename)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetFileName](#getfilename)합니다.

##  <a name="getlength"></a>  CFile::GetLength

바이트에 있는 파일의 현재 논리적 길이 가져옵니다.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>반환 값

파일의 길이입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

##  <a name="getposition"></a>  CFile::GetPosition

에 대 한 후속 호출에서 사용할 수 있는 파일 포인터의 현재 값을 가져와 `Seek`합니다.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>반환 값

파일 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

##  <a name="getstatus"></a>  CFile::GetStatus

와 관련 된 상태 정보를 검색 하는이 메서드는 지정 된 `CFile` 개체 인스턴스 또는 지정 된 파일 경로입니다.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*rStatus*<br/>
사용자가 제공한에 대 한 참조 `CFileStatus` 상태 정보를 받는 구조체입니다. `CFileStatus` 구조에는 다음 필드가 있습니다.

- `CTime m_ctime` 날짜 및 파일을 만든 시간입니다.

- `CTime m_mtime` 날짜 및 파일을 마지막으로 수정한 시간입니다.

- `CTime m_atime` 날짜 및 읽기에 대 한 파일에 마지막으로 액세스 하는 시간입니다.

- `ULONGLONG m_size` 논리 크기 (바이트)를 DIR 명령으로 보고 된 파일입니다.

- `BYTE m_attribute` 파일의 특성 바이트입니다.

- `char m_szFullName[_MAX_PATH]` Windows 문자 집합에 절대 파일 이름입니다.

*lpszFileName*<br/>
원하는 파일을 Windows 문자의 문자열로 설정 경로입니다. 상대 또는 절대 경로일 수 있습니다 또는 네트워크 경로 이름을 포함할 수 있습니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="return-value"></a>반환 값

TRUE 이면 지정된 된 파일에 대 한 상태 정보를 성공적으로 가져온; 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

Static이 아닌 버전의 `GetStatus` 와 연결 된 열려 있는 파일의 상태 정보를 검색 합니다 지정 `CFile` 개체입니다.  정적 버전 `GetStatus` 실제로 파일을 열지 않고 지정 된 파일 경로에서 파일 상태를 가져옵니다. 파일의 존재 여부 및 액세스 권한이 테스트에 유용 합니다.

합니다 `m_attribute` 의 멤버는 `CFileStatus` 구조 파일 특성 집합을 나타냅니다. 합니다 `CFile` 클래스를 제공 합니다 **특성** 파일 특성을 상징적으로 지정할 수 있도록 열거형 형식:

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

##  <a name="hfilenull"></a>  CFile::hFileNull

에 대 한 유효한 파일 핸들의 현재 상태를 결정 합니다 `CFile` 개체입니다.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>설명

이 상수 확인에 사용 되는 `CFile` 개체에 유효한 파일 핸들입니다.

다음 예제에서는이 작업을 보여 줍니다.

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

##  <a name="lockrange"></a>  CFile::LockRange

파일이 이미 잠겨 있는 경우 예외를 throw 하는 열려 있는 파일에서 바이트 범위를 잠급니다.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>매개 변수

*dwPos*<br/>
잠글 바이트 범위 시작의 바이트 오프셋입니다.

*dwCount*<br/>
잠글 범위의의 바이트 수입니다.

### <a name="remarks"></a>설명

파일의 바이트를 잠그면 다른 프로세스에서 해당 바이트에 액세스할 수 없습니다. 파일의 둘 이상의 영역을 잠글 수 있습니다 하지만 없습니다 겹치는 영역을 사용할 수는 있습니다.

지역의 잠금을 해제 하면 사용 하 여 `UnlockRange` 멤버 함수는 바이트 범위 이전에 잠근 지역으로 정확 하 게 일치 해야 합니다. `LockRange` 각 영역을 별도로 잠금 해제 해야 잠긴된 두 영역이 인접 한 경우; 함수는 인접 한 영역을 병합 하지 않습니다.

> [!NOTE]
>  이 함수를 사용할 수 없는 경우는 `CMemFile`-클래스를 파생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="m_hfile"></a>  CFile::m_hFile

열려 있는 파일에 대 한 운영 체제 파일 핸들을 포함합니다.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>설명

`m_hFile` UINT 형식의 공용 변수가입니다. 포함 된 `CFile::hFileNull` (운영 체제-독립적인 빈 파일 표시기) 핸들을 할당 되지 않은 경우.

사용 `m_hFile` 멤버의 의미는 파생된 클래스에 따라 달라 지므로 권장 되지 않습니다. `m_hFile` 비 다형 지원에 편의 위해 공용 멤버 클래스의 사용 됩니다.

##  <a name="m_ptm"></a>  CFile::m_pTM

`CAtlTransactionManager` 개체에 대한 포인터입니다.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>설명

##  <a name="open"></a>  CFile::Open

오버로드됨. `Open` 기본적으로 사용 하도록 설계 된 `CFile` 생성자입니다.

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
문자열은 원하는 파일을 경로입니다. Relative, absolute, 또는 네트워크 이름 (UNC) 경로 수 있습니다.

*nOpenFlags*<br/>
파일의 공유 및 액세스 모드를 정의 하는 UINT 합니다. 파일을 열 때 수행할 동작을 지정 합니다. 비트 OR를 사용 하 여 옵션을 결합할 수 있습니다 ( **&#124;** ) 연산자. 에 대 한 액세스 권한과 하나 공유 옵션은 필요한; 합니다 `modeCreate` 고 `modeNoInherit` 모드는 선택 사항입니다. 참조 된 [CFile](#cfile) 모드 옵션의 목록에 대 한 생성자입니다.

*pError*<br/>
실패 한 작업의 상태를 수신 하는 기존 파일 예외 개체에 대 한 포인터입니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="return-value"></a>반환 값

열기에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다. 합니다 *pError* 매개 변수는 0이 반환 하는 경우에 유효 합니다.

### <a name="remarks"></a>설명

두 함수는 오류는 일반적으로 필요한 조건을이 파일을 열기 위한 "안전" 메서드를 형성 합니다.

하지만 합니다 `CFile` 생성자는 오류 조건에서는 예외가 throw 됩니다 `Open` 오류 조건에 대해 FALSE를 반환 합니다. `Open` 하지만 여전히 초기화할 수는 [CFileException](../../mfc/reference/cfileexception-class.md) 오류를 설명 하는 개체입니다. 제공 하지 않으면 합니다 *pError* 매개 변수를 NULL을 전달 하는 경우 또는 *pError*, `Open` FALSE를 반환 하 고 throw 하지는 `CFileException`. 기존에 대 한 포인터를 전달 하면 `CFileException`, 및 `Open` 에서 오류가 발생 하는 함수는 채울 해당 오류를 설명 하는 정보입니다. 사례는 모두에서 `Open` 예외를 throw 합니다.

다음 표에서 가능한 결과 `Open`합니다.

|`pError`|오류가 발생 했습니다.|반환 값|CFileException 콘텐츠|
|--------------|------------------------|------------------|----------------------------|
|NULL|아니요|TRUE|N/A|
|에 ptr `CFileException`|아니요|TRUE|변경 안 됨|
|NULL|예|FALSE|N/A|
|에 ptr `CFileException`|예|FALSE|오류 설명으로 초기화|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

##  <a name="operator_handle"></a>  CFile::operator HANDLE

이 연산자를 사용 하 여에 대 한 핸들을 전달 하는 `CFile` 와 같은 함수 개체 [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) 및 [GetFileTime](/windows/desktop/api/fileapi/nf-fileapi-getfiletime) 는 `HANDLE`합니다.

```
operator HANDLE() const;
```

##  <a name="read"></a>  CFile::Read

연결 된 파일에서 버퍼에 데이터를 읽는 `CFile` 개체입니다.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
파일에서 읽은 데이터를 수신 하는 사용자가 제공한 버퍼에 대 한 포인터입니다.

*nCount*<br/>
파일에서 읽을 바이트의 최대 수입니다. 텍스트 모드 파일의 경우 캐리지 리턴-줄 바꿈 쌍을 단일 문자로 계산 됩니다.

### <a name="return-value"></a>반환 값

버퍼로 전송된 바이트 수입니다. 모든 유의 `CFile` 클래스, 반환 값 수 미만 *nCount* 파일의 끝에 도달한 경우입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

다른 예제를 참조 하세요. [CFile::Open](#open)합니다.

##  <a name="remove"></a>  CFile::Remove

이 정적 함수는 경로 의해 지정 된 파일을 삭제 합니다.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
문자열은 원하는 파일을 경로입니다. 경로 상대 또는 절대 수 있으며 네트워크 이름을 포함할 수 있습니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

디렉터리를 제거 하지 않습니다.

`Remove` 멤버 함수는 열려 있는 연결 된 파일 또는 파일을 제거할 수 없는 경우 예외를 throw 합니다. DEL 명령을 하는 것과 같습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

##  <a name="rename"></a>  CFile::Rename

이 정적 함수는 지정된 된 파일을 이름을 바꿉니다.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszOldName*<br/>
이전 경로입니다.

*lpszNewName*<br/>
새 경로입니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

디렉터리의 이름을 바꿀 수 없습니다. REN 명령에는 것과 같습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

##  <a name="seek"></a>  CFile::Seek

열려 있는 파일에서 파일 포인터 위치를 변경 합니다.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>매개 변수

*lOff*<br/>
파일 포인터를 이동 하는 바이트 수입니다. 파일의 끝 쪽 파일 포인터를 이동 하는 양수 값 음수 값은 파일의 시작 부분 쪽으로 파일 포인터를 이동 합니다.

*nFrom*<br/>
검색할 위치입니다. 가능한 값에 대 한 설명 섹션을 참조 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 파일 포인터의 위치 반환 값은 정의 된 그렇지 않은 경우에 대 한 포인터를 `CFileException` 예외가 throw 됩니다.

### <a name="remarks"></a>설명

다음 표에 대 한 가능한 값은 *nFrom* 매개 변수입니다.

|값|설명|
|-----------|-----------------|
|`CFile::begin`|파일의 시작 부분에서 검색 합니다.|
|`CFile::current`|파일 포인터의 현재 위치에서 검색 합니다.|
|`CFile::end`|파일의 끝에서 검색 합니다.|

파일을 열면 파일 포인터는 0으로 파일의 시작에 배치 됩니다.

파일의 끝을 넘어 위치로 파일 포인터를 설정할 수 있습니다. 이렇게 하면 파일에 쓸 때까지 파일의 크기 증가 하지 않습니다.

이 메서드에 대 한 예외 처리기는 예외 처리 된 후 예외 개체를 삭제 해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

##  <a name="seektobegin"></a>  CFile::SeekToBegin

파일의 시작 부분으로 파일 포인터의 값을 설정 합니다.

```
void SeekToBegin();
```

### <a name="remarks"></a>설명

`SeekToBegin()`는 `Seek( 0L, CFile::begin )`와 같습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="seektoend"></a>  CFile::SeekToEnd

파일의 논리적 끝에 파일 포인터의 값을 설정 합니다.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>반환 값

파일의 길이(바이트)입니다.

### <a name="remarks"></a>설명

`SeekToEnd()`는 `CFile::Seek( 0L, CFile::end )`와 같습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="setfilepath"></a>  CFile::SetFilePath

파일의 경로 지정 하려면이 함수를 호출 합니다. 예를 들어 파일의 경로 사용할 수 없는 경우는 [CFile](../../mfc/reference/cfile-class.md) 개체가 생성 되 면 호출 `SetFilePath` 제공 합니다.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>매개 변수

*lpszNewName*<br/>
새 경로 지정 하는 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> `SetFilePath` 파일을 열고 하지 않거나 파일 만들기 단순히 연결을 `CFile` 경로 이름으로 사용할 수 있는 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

##  <a name="setlength"></a>  CFile::SetLength

파일의 길이 변경 하려면이 함수를 호출 합니다.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>매개 변수

*dwNewLen*<br/>
바이트에 있는 파일의 원하는 길이입니다. 이 값은 파일의 현재 길이 보다 크거나 작을 수 있습니다. 파일 확장 되거나 적절 하 게 잘립니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  사용 하 여 `CMemFile`,이 함수가 throw 할 수는 `CMemoryException` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

##  <a name="setstatus"></a>  CFile::SetStatus

이 파일 위치와 연결 된 파일의 상태를 설정 합니다.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
문자열은 원하는 파일을 경로입니다. 경로 상대 또는 절대 수 있으며 네트워크 이름을 포함할 수 있습니다.

*status*<br/>
새 상태 정보가 들어 있는 버퍼입니다. 호출을 `GetStatus` prefill 멤버 함수는 `CFileStatus` 현재 값을 사용 하 여 구조체를 필요에 따라 변경 합니다. 값이 0 이면 해당 상태 항목이 업데이트 되지 않습니다. 참조를 [GetStatus](#getstatus) 에 대 한 멤버 함수는 `CFileStatus` 구조입니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

수정 시간을 설정 하는 `m_mtime` 필드에 *상태*합니다.

유의 사항에 대 한 호출을 하는 경우 `SetStatus` 만 파일의 특성을 변경 하려고 하며 `m_mtime` 파일 상태 구조체의 멤버 이면 0이 아닌 특성을 영향을 받습니다 (-시간 스탬프에 부작용을 미칠 수를 변경 하는 중 특성)입니다. 만 파일의 특성을 변경 하려는 경우 먼저 설정 합니다 `m_mtime` 0 및 다음에 대 한 호출을 확인 하는 파일 상태 구조체의 멤버 `SetStatus`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

##  <a name="unlockrange"></a>  CFile::UnlockRange

열려 있는 파일에서 바이트 범위 잠금을 해제합니다.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>매개 변수

*dwPos*<br/>
바이트 범위 잠금을 해제 하려면 시작의 바이트 오프셋입니다.

*dwCount*<br/>
잠금을 해제할 범위의의 바이트 수입니다.

### <a name="remarks"></a>설명

에 대 한 설명을 참조 합니다 [LockRange](#lockrange) 세부 정보에 대 한 멤버 함수입니다.

> [!NOTE]
>  이 함수를 사용할 수 없는 경우는 `CMemFile`-클래스를 파생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="write"></a>  CFile::Write

버퍼에서 데이터를 연결 된 파일을 쓸는 `CFile` 개체입니다.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
파일에 쓸 데이터를 포함 하는 사용자가 제공한 버퍼에 대 한 포인터입니다.

*nCount*<br/>
버퍼에서 전송할 바이트 수입니다. 텍스트 모드 파일의 경우 캐리지 리턴-줄 바꿈 쌍을 단일 문자로 계산 됩니다.

### <a name="remarks"></a>설명

`Write` 디스크 꽉 참 조건을 포함 하 여 여러 조건에 대 한 응답에서 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

또한 예제를 참조 하십시오 [CFile::CFile](#cfile) 하 고 [CFile::Open](#open)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CStdioFile 클래스](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemFile 클래스](../../mfc/reference/cmemfile-class.md)
