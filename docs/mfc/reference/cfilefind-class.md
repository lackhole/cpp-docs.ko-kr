---
title: CFileFind 클래스
ms.date: 11/04/2016
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
ms.openlocfilehash: 5534b61b3c588c79c0120f1a5bc8064b5a605e8a
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503787"
---
# <a name="cfilefind-class"></a>CFileFind 클래스

로컬 파일 검색을 수행 하 고에 대 한 기본 클래스인 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 하 고 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), 인터넷 파일 검색을 수행 하는 합니다.

## <a name="syntax"></a>구문

```
class CFileFind : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFileFind::CFileFind](#cfilefind)|`CFileFind` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFileFind::Close](#close)|검색 요청을 종결 합니다.|
|[CFileFind::FindFile](#findfile)|지정된 된 파일 이름에 대 한 디렉터리를 검색합니다.|
|[CFileFind::FindNextFile](#findnextfile)|파일 검색에 대 한 이전 호출에서 계속 [FindFile](#findfile)합니다.|
|[CFileFind::GetCreationTime](#getcreationtime)|파일을 만든 시간을 가져옵니다.|
|[CFileFind::GetFileName](#getfilename)|찾은 파일의 확장명을 포함 하는 이름을 가져옵니다.|
|[CFileFind::GetFilePath](#getfilepath)|찾은 파일의 전체 경로 가져옵니다.|
|[CFileFind::GetFileTitle](#getfiletitle)|찾은 파일의 제목을 가져옵니다. 제목을 확장을 다루지 않습니다.|
|[CFileFind::GetFileURL](#getfileurl)|찾은 파일의 파일 경로 포함 하 여 URL을 가져옵니다.|
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|파일에 마지막으로 액세스 하는 시간을 가져옵니다.|
|[CFileFind::GetLastWriteTime](#getlastwritetime)|파일을 마지막으로 변경 되 고 저장 된 시간을 가져옵니다.|
|[CFileFind::GetLength](#getlength)|바이트에서 찾은 파일의 길이 가져옵니다.|
|[CFileFind::GetRoot](#getroot)|찾은 파일의 루트 디렉터리를 가져옵니다.|
|[CFileFind::IsArchived](#isarchived)|찾은 파일을 보관 하는 경우를 결정 합니다.|
|[CFileFind::IsCompressed](#iscompressed)|검색된 된 파일은 압축 하는 경우를 결정 합니다.|
|[CFileFind::IsDirectory](#isdirectory)|검색된 된 파일 디렉터리 인지 확인 합니다.|
|[CFileFind::IsDots](#isdots)|검색된 된 파일 이름의 이름 인지 여부를 결정 "."또는"..."를 실제 디렉터리를 나타내는입니다.|
|[CFileFind::IsHidden](#ishidden)|찾은 파일 숨겨지는지 여부를 결정 합니다.|
|[CFileFind::IsNormal](#isnormal)|찾은 파일 정상 인지 여부를 확인 (즉, 다른 특성이 없는).|
|[CFileFind::IsReadOnly](#isreadonly)|읽기 전용으로 검색된 된 파일 인지 확인 합니다.|
|[CFileFind::IsSystem](#issystem)|검색된 된 파일 시스템 파일 인지 확인 합니다.|
|[CFileFind::IsTemporary](#istemporary)|찾은 파일 임시 인지 확인 합니다.|
|[CFileFind::MatchesMask](#matchesmask)|찾을 수 파일의 원하는 파일 특성을 나타냅니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CFileFind::CloseContext](#closecontext)|현재 검색 핸들에 의해 지정 된 파일을 닫습니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFileFind::m_pTM](#m_ptm)|`CAtlTransactionManager` 개체에 대한 포인터입니다.|

## <a name="remarks"></a>설명

`CFileFind` 검색을 시작, 파일을 찾아, 제목, 이름 또는 파일의 경로 반환 하는 멤버 함수를 포함 합니다. 인터넷 검색, 멤버 함수에 대 한 [GetFileURL](#getfileurl) 파일의 URL을 반환 합니다.

`CFileFind` 다른 두 MFC 클래스에 대 한 기본 클래스를 검색 하도록 특정 서버 유형: `CGopherFileFind` gopher 서버, 특히 작동 및 `CFtpFileFind` FTP 서버를 사용 하 여 구체적으로 작동 합니다. 함께 이러한 세 가지 클래스 서버 프로토콜, 파일 형식 또는 위치에 관계 없이 로컬 컴퓨터 또는 원격 서버에서 파일을 찾으려면 클라이언트 원활 하 게 메커니즘을 제공 합니다.

다음 코드는 각 파일의 이름을 인쇄 현재 디렉터리의 모든 파일을 열거:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

이 코드에서는 간단히 유지 하기 위해이 예제에서는 다음을 사용 합니다.는 C++ 표준 라이브러리 `cout` 클래스입니다. 합니다 `cout` 줄에 대 한 호출을 사용 하 여 바꿀 수 없습니다 `CListBox::AddString`, 예를 들어 그래픽 사용자 인터페이스를 사용 하 여 프로그램에서 합니다.

사용 하는 방법에 대 한 자세한 내용은 `CFileFind` 문서를 참조 하는 다른 WinInet 클래스 및 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="cfilefind"></a>  CFileFind::CFileFind

이 멤버 함수를 호출 하는 경우는 `CFileFind` 개체가 생성 됩니다.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>매개 변수

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetFileName](#getfilename)합니다.

##  <a name="close"></a>  CFileFind::Close

검색 종료 하는 컨텍스트를 다시 설정 하 고 모든 리소스를 해제 하려면이 멤버 함수를 호출 합니다.

```
void Close();
```

### <a name="remarks"></a>설명

호출한 후 `Close`를 새로 만들 필요가 없습니다 `CFileFind` 호출 하기 전에 인스턴스 [FindFile](#findfile) 새 검색을 시작 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetFileName](#getfilename)합니다.

##  <a name="closecontext"></a>  CFileFind::CloseContext

현재 검색 핸들에 의해 지정 된 파일을 닫습니다.

```
virtual void CloseContext();
```

### <a name="remarks"></a>설명

검색 핸들의 현재 값으로 지정 된 파일을 닫습니다. 기본 동작을 변경 하려면이 함수를 재정의 합니다.

호출 해야 합니다는 [FindFile](#findfile) 또는 [FindNextFile](#findnextfile) 함수를 한 번 이상 유효한 검색 핸들을 가져올 수 있습니다. 합니다 `FindFile` 및 `FindNextFile` 함수 이름이 지정 된 이름과 일치 하는 파일을 찾는 검색 핸들을 사용 합니다.

##  <a name="findfile"></a>  CFileFind::FindFile

파일 검색을 열려면이 멤버 함수를 호출 합니다.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>매개 변수

*pstrName*<br/>
검색할 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다. NULL을 전달 하는 경우 *pstrName*를 `FindFile` 는 와일드 카드 (*.\*) 검색 합니다.

*dwUnused*<br/>
확인 하기 위해 예약 된 `FindFile` 파생 클래스 다형 합니다. 0이어야 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 가져오기, Win32 함수 호출 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)합니다.

### <a name="remarks"></a>설명

호출한 후 `FindFile` 파일 검색을 시작 하려면 호출 [FindNextFile](#findnextfile) 후속 파일을 검색 합니다. 호출 해야 `FindNextFile` 다음 특성의 모든 멤버 함수를 호출 하기 전에 한 번 이상:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [IsArchived](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::IsDirectory](#isdirectory)합니다.

##  <a name="findnextfile"></a>  CFileFind::FindNextFile

이전 호출에서 파일을 검색 하려면이 멤버 함수 호출 [FindFile](#findfile)합니다.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>반환 값

더 많은 파일; 없으면 0이 아닌 값 파일을 찾을 수는 디렉터리에 마지막 또는 오류가 발생 한 경우 0입니다. 확장 오류 정보를 가져오기, Win32 함수 호출 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)합니다. 찾은 파일 디렉터리에 마지막 파일 되었거나 일치 하는 경우에 파일을 찾을 수 있습니다는 `GetLastError` ERROR_NO_MORE_FILES를 반환 합니다.

### <a name="remarks"></a>설명

호출 해야 `FindNextFile` 다음 특성의 모든 멤버 함수를 호출 하기 전에 한 번 이상:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [IsArchived](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

`FindNextFile` Win32 함수를 래핑하고 [FindNextFile](/windows/desktop/api/fileapi/nf-fileapi-findnextfilea)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::IsDirectory](#isdirectory)합니다.

##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime

지정된 된 파일을 만든 시간을 가져오려면이 함수를 호출 합니다.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>매개 변수

*pTimeStamp*<br/>
에 대 한 포인터를 [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) 파일을 만든 시간을 포함 하는 구조입니다.

*refTime*<br/>
에 대 한 참조를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 실패 한 경우 0입니다. `GetCreationTime` 경우에 0을 반환 합니다 [FindNextFile](#findnextfile) 이 호출한 적 `CFileFind` 개체입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetCreationTime`합니다.

> [!NOTE]
>  일부 파일 시스템에서는 동일한 의미 체계를 사용 하 여이 함수에서 반환 된 타임 스탬프를 구현 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조 된 [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간은 영역 로컬 컴퓨터에 파일이 배치 된 시간에서입니다. Win32를 참조 하세요 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API 자세한 정보.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="getfilename"></a>  CFileFind::GetFileName

찾은 파일의 이름을 가져오려면이 함수를 호출 합니다.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>반환 값

가장 최근에 찾은 파일의 이름입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) GetFileName를 호출 하기 전에 한 번 이상.

`GetFileName` 3 중 하나인 `CFileFind` 일종의 파일 이름 반환 하는 멤버 함수입니다. 다음 목록에는 세 가지 및 다는 방법을 설명 합니다.

- `GetFileName` 확장명을 포함 하는 파일 이름을 반환 합니다. 예를 들어, 호출 `GetFileName` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 파일 이름을 반환 *myfile.txt*합니다.

- [GetFilePath](#getfilepath) 파일의 전체 경로 반환 합니다. 예를 들어, 호출 `GetFilePath` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 파일 경로 반환 *c:\myhtml\myfile.txt*합니다.

- [GetFileTitle](#getfiletitle) 파일 확장명 제외 하 고 파일 이름을 반환 합니다. 예를 들어, 호출 `GetFileTitle` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 제목을 반환 하는 파일 *myfile*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

##  <a name="getfilepath"></a>  CFileFind::GetFilePath

지정된 된 파일의 전체 경로를 가져오지이 멤버 함수를 호출 합니다.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>반환 값

지정된 된 파일의 경로입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetFilePath`합니다.

`GetFilePath` 3 중 하나인 `CFileFind` 일종의 파일 이름 반환 하는 멤버 함수입니다. 다음 목록에는 세 가지 및 다는 방법을 설명 합니다.

- [GetFileName](#getfilename) 확장명을 포함 하는 파일 이름을 반환 합니다. 예를 들어, 호출 `GetFileName` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 파일 이름을 반환 *myfile.txt*합니다.

- `GetFilePath` 파일의 전체 경로 반환합니다. 예를 들어, 호출 `GetFilePath` 파일에 대 한 사용자 메시지를 생성할 `c:\myhtml\myfile.txt` 파일 경로 반환 `c:\myhtml\myfile.txt`합니다.

- [GetFileTitle](#getfiletitle) 파일 확장명 제외 하 고 파일 이름을 반환 합니다. 예를 들어, 호출 `GetFileTitle` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 제목을 반환 하는 파일 *myfile*합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetFileName](#getfilename)합니다.

##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle

찾은 파일의 제목이 멤버 함수를 호출 합니다.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>반환 값

파일의 제목입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetFileTitle`합니다.

`GetFileTitle` 3 중 하나인 `CFileFind` 일종의 파일 이름 반환 하는 멤버 함수입니다. 다음 목록에는 세 가지 및 다는 방법을 설명 합니다.

- [GetFileName](#getfilename) 확장명을 포함 하는 파일 이름을 반환 합니다. 예를 들어, 호출 `GetFileName` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 파일 이름을 반환 *myfile.txt*합니다.

- [GetFilePath](#getfilepath) 파일의 전체 경로 반환 합니다. 예를 들어, 호출 `GetFilePath` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 파일 경로 반환 *c:\myhtml\myfile.txt*합니다.

- `GetFileTitle` 파일 확장명 제외 하 고 파일 이름을 반환 합니다. 예를 들어, 호출 `GetFileTitle` 파일에 대 한 사용자 메시지를 생성할 *c:\myhtml\myfile.txt* 제목을 반환 하는 파일 *myfile*합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetFileName](#getfilename)합니다.

##  <a name="getfileurl"></a>  CFileFind::GetFileURL

지정된 된 URL을 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>반환 값

전체 URL입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetFileURL`합니다.

`GetFileURL` 멤버 함수에 비슷합니다 [GetFilePath](#getfilepath)형태로 URL을 반환 하는 점을 제외 하 고, `file://path`합니다. 예를 들어, 호출 `GetFileURL` 에 대 한 전체 URL을 가져오려면 *myfile.txt* URL을 반환 합니다 `file://c:\myhtml\myfile.txt`합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetFileName](#getfilename)합니다.

##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime

지정된 된 파일에 마지막으로 액세스 하는 시간을 가져오려면이 함수를 호출 합니다.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>매개 변수

*refTime*<br/>
에 대 한 참조를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.

*pTimeStamp*<br/>
에 대 한 포인터를 [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) 파일을 마지막으로 액세스 한 시간을 포함 하는 구조체.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 실패 한 경우 0입니다. `GetLastAccessTime` 경우에 0을 반환 합니다 [FindNextFile](#findnextfile) 이 호출한 적 `CFileFind` 개체입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastAccessTime`합니다.

> [!NOTE]
>  일부 파일 시스템에서는 동일한 의미 체계를 사용 하 여이 함수에서 반환 된 타임 스탬프를 구현 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조 된 [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간은 영역 로컬 컴퓨터에 파일이 배치 된 시간에서입니다. Win32를 참조 하세요 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API 자세한 정보.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime

파일을 변경한 마지막 시간을 가져오려면이 함수를 호출 합니다.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>매개 변수

*pTimeStamp*<br/>
에 대 한 포인터를 [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) 파일에 마지막으로 쓴 시간을 포함 하는 구조입니다.

*refTime*<br/>
에 대 한 참조를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 실패 한 경우 0입니다. `GetLastWriteTime` 경우에 0을 반환 합니다 [FindNextFile](#findnextfile) 이 호출한 적 `CFileFind` 개체입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastWriteTime`합니다.

> [!NOTE]
>  일부 파일 시스템에서는 동일한 의미 체계를 사용 하 여이 함수에서 반환 된 타임 스탬프를 구현 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조 된 [Win32_Find_Data](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간은 영역 로컬 컴퓨터에 파일이 배치 된 시간에서입니다. Win32를 참조 하세요 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API 자세한 정보.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="getlength"></a>  CFileFind::GetLength

이 바이트에 있는 파일의 길이를 가져오는 함수를 호출 합니다.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>반환 값

바이트에서 찾은 파일의 길이입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLength`합니다.

`GetLength` Win32 구조를 사용 하 여 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 를 가져오고 파일 크기의 값을 바이트 단위로 반환 합니다.

> [!NOTE]
>  MFC 7.0부터 `GetLength` 64 비트 정수 형식을 지원 합니다. 이전에이 최신 버전의 라이브러리를 사용 하 여 빌드한 기존 코드 잘림 경고가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

##  <a name="getroot"></a>  CFileFind::GetRoot

찾은 파일의 루트를 가져오려면이 함수를 호출 합니다.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>반환 값

활성 검색의 루트입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetRoot`합니다.

이 멤버 함수는 드라이브 지정자 및 검색을 시작 하는 데 사용 하는 경로 이름을 반환 합니다. 예를 들어, 호출 [FindFile](#findfile) 사용 하 여 `*.dat` 결과 `GetRoot` 빈 문자열을 반환 합니다. 같은 경로 전달 `c:\windows\system\*.dll`를 `FindFile` 결과 `GetRoot` 반환 `c:\windows\system\`합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetFileName](#getfilename)합니다.

##  <a name="isarchived"></a>  CFileFind::IsArchived

찾은 파일을 보관 하는 경우를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램에 백업 하거나 FILE_ATTRIBUTE_ARCHIVE에서 식별 된 파일 특성을 사용 하 여 제거 하는 보관 파일을 표시 합니다 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsArchived`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="iscompressed"></a>  CFileFind::IsCompressed

검색된 된 파일은 압축 하는 경우를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

압축된 된 파일은 FILE_ATTRIBUTE_COMPRESSED 기본적으로, 파일 특성에 나오는 합니다 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다. 파일의 경우이 특성의 모든 파일에 데이터 압축은 나타냅니다. 디렉터리의 경우이 특성 압축 새로 만들어진 파일과 하위 디렉터리에 대 한 기본 임을 나타냅니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsCompressed`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="isdirectory"></a>  CFileFind::IsDirectory

검색된 된 파일 디렉터리 인지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

디렉터리는 파일로 FILE_ATTRIBUTE_DIRECTORY에서 식별 된 파일 특성으로 표시 됩니다는 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsDirectory`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

이 작은 프로그램 C:\ 드라이브의 모든 디렉터리 재귀 및 디렉터리의 이름을 출력 합니다.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

##  <a name="isdots"></a>  CFileFind::IsDots

현재 디렉터리 및 부모 디렉터리 표식에 대 한 파일을 반복 하는 동안 테스트 하려면이 멤버 함수를 호출 합니다.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>반환 값

찾은 파일 이름을 가진 경우 0이 아닌 "."또는"..."를 실제 디렉터리를 찾은 파일 임을 나타냅니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsDots`합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::IsDirectory](#isdirectory)합니다.

##  <a name="ishidden"></a>  CFileFind::IsHidden

찾은 파일 숨겨져 있는지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

FILE_ATTRIBUTE_HIDDEN으로 표시 되는 숨겨진된 파일을 파일 특성을 식별 합니다 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다. 숨겨진된 파일을 일반 디렉터리 목록에 포함 되지 않습니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsHidden`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="isnormal"></a>  CFileFind::IsNormal

검색된 된 파일을 일반 파일 인지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

FILE_ATTRIBUTE_NORMAL으로 표시 된 파일, 파일 특성을 식별 합니다 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다. 일반 파일에 다른 특성 집합이 없습니다. 다른 모든 파일 특성이이 특성을 재정의 합니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsNormal`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="isreadonly"></a>  CFileFind::IsReadOnly

찾은 파일 읽기 전용인 지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

읽기 전용 파일은 FILE_ATTRIBUTE_READONLY 기본적으로, 파일 특성에 나오는 합니다 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다. 응용 프로그램에는 이러한 파일을 읽을 수 있지만를 작성 하거나 삭제할 수는 없습니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsReadOnly`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="issystem"></a>  CFileFind::IsSystem

검색된 된 파일 시스템 파일 인지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

시스템 파일은 FILE_ATTRIBUTE_SYSTEM, 기본적으로, 파일 특성에서 식별 된 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다. 시스템 파일의 일부인 또는 단독으로, 운영 체제에서 사용 됩니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsSystem`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="istemporary"></a>  CFileFind::IsTemporary

임시 파일을 찾은 파일 인지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

임시 파일은 FILE_ATTRIBUTE_TEMPORARY 기본적으로, 파일 특성에서 식별 된 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조입니다. 임시 파일을 임시로 저장 됩니다. 응용 프로그램은 반드시 필요한 경우에 파일에 작성 해야 합니다. 대부분의 파일의 데이터 파일을 곧 삭제 되므로 미디어에 플러시되고 하지 않고 메모리에 남아 있습니다.

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsTemporary`합니다.

멤버 함수를 참조 하세요 [MatchesMask](#matchesmask) 파일 특성의 목록은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFileFind::GetLength](#getlength)합니다.

##  <a name="m_ptm"></a>  CFileFind::m_pTM

`CAtlTransactionManager` 개체에 대한 포인터입니다.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>설명

##  <a name="matchesmask"></a>  CFileFind::MatchesMask

찾은 파일의 파일 특성을 테스트 하려면이 멤버 함수를 호출 합니다.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>매개 변수

*dwMask*<br/>
식별 된 하나 이상의 파일 특성을 지정 합니다 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 구조를 검색된 합니다. 비트 OR를 사용 하 여 여러 특성을 검색 하려면 (&#124;) 연산자. 다음 특성의 조합을 허용 됩니다.

- FILE_ATTRIBUTE_ARCHIVE 파일 보관 파일입니다. 응용 프로그램 백업 또는 제거에 대 한 파일을 표시 하려면이 특성을 사용 합니다.

- 파일 또는 디렉터리 FILE_ATTRIBUTE_COMPRESSED 압축 됩니다. 파일을 압축 파일에서 데이터를 모두 의미 합니다. 디렉터리를 새로 만들어진 파일과 하위 디렉터리에 대 한 기본 압축 임을 의미 합니다.

- FILE_ATTRIBUTE_DIRECTORY 파일 디렉터리입니다.

- FILE_ATTRIBUTE_NORMAL 파일에 다른 특성 집합이 없습니다. 이 특성은 단독으로 사용 하는 경우에 유효 합니다. 다른 모든 파일 특성이이 특성을 재정의 합니다.

- FILE_ATTRIBUTE_HIDDEN 파일 숨겨집니다. 일반 디렉터리 목록에 포함 하지 않습니다.

- FILE_ATTRIBUTE_READONLY 파일 읽기 전용입니다. 응용 프로그램 파일을 읽을 수 있지만 쓸 하거나 삭제할 수 없습니다.

- FILE_ATTRIBUTE_SYSTEM 파일의 일부 이거나 운영 체제에서 독점적으로 사용 됩니다.

- 임시 저장소에 대 한 FILE_ATTRIBUTE_TEMPORARY 파일을 사용 중입니다. 응용 프로그램은 반드시 필요한 경우에 파일에 작성 해야 합니다. 대부분의 파일의 데이터 파일을 곧 삭제 되므로 미디어에 플러시되고 하지 않고 메모리에 남아 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 가져오기, Win32 함수 호출 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)합니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `MatchesMask`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind 클래스](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind 클래스](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
