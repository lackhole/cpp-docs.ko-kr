---
title: CGopherFileFind 클래스
ms.date: 11/04/2016
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
ms.openlocfilehash: bced5a95f65713915a1f06094bfe059db79aab2d
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503636"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind 클래스

Gopher 서버의 인터넷 파일 검색에 유용합니다.

> [!NOTE]
>  클래스 `CGopherConnection`, `CGopherFile`를 `CGopherFileFind`, `CGopherLocator` 및 해당 멤버는 사용 되지 않습니다 Windows XP 플랫폼에서 작동 하지 않습니다 하지만 계속 이전 플랫폼에서 작동 합니다.

## <a name="syntax"></a>구문

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|`CGopherFileFind` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CGopherFileFind::FindFile](#findfile)|Gopher 서버에서 파일을 찾습니다.|
|[CGopherFileFind::FindNextFile](#findnextfile)|파일 검색에 대 한 이전 호출에서 계속 [FindFile](#findfile)합니다.|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|지정 된 파일을 만든 시간을 가져옵니다.|
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|지정된 된 파일을 마지막으로 액세스 한 시간을 가져옵니다.|
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|지정된 된 파일에 마지막으로 쓴 시간을 가져옵니다.|
|[CGopherFileFind::GetLength](#getlength)|바이트에서 찾은 파일의 길이 가져옵니다.|
|[CGopherFileFind::GetLocator](#getlocator)|가져오기는 `CGopherLocator` 개체입니다.|
|[CGopherFileFind::GetScreenName](#getscreenname)|Gopher 화면 이름을 가져옵니다.|
|[CGopherFileFind::IsDots](#isdots)|파일을 반복 하는 동안 현재 디렉터리 및 부모 디렉터리 표식에 대 한 테스트 합니다.|

## <a name="remarks"></a>설명

`CGopherFileFind` 검색을 시작 파일을 찾아 파일의 URL을 반환 하는 멤버 함수를 포함 합니다.

인터넷 및 검색 하는 로컬 파일 포함을 위해 설계 된 다른 MFC 클래스 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) 하 고 [CFileFind](../../mfc/reference/cfilefind-class.md)합니다. 와 함께 `CGopherFileFind`, 서버 프로토콜, 파일 형식 또는 위치 (로컬 컴퓨터 또는 원격 서버입니다.)에 관계 없이 특정 파일을 찾는 사용자에 대 한 완벽 한 메커니즘을 제공 하는 이러한 클래스 HTTP 검색에 필요한 파일을 직접 조작을 지원 하지 않으므로 HTTP 서버에서 검색 하는 데 없는 MFC 클래스는 참고 합니다.

> [!NOTE]
> `CGopherFileFind` 기본 클래스의 다음 멤버 함수를 지원 하지 않습니다 [CFileFind](../../mfc/reference/cfilefind-class.md):

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

또한을 사용 하는 경우에 `CGopherFileFind`서 `CFileFind` 멤버 함수 [IsDots](../../mfc/reference/cfilefind-class.md#isdots) 항상 FALSE입니다.

사용 하는 방법에 대 한 자세한 내용은 `CGopherFileFind` 문서를 참조 하는 다른 WinInet 클래스 및 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind

이 멤버 함수를 생성 하 라고는 `CGopherFileFind` 개체입니다.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pConnection*<br/>
에 대 한 포인터를 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 개체입니다.

*dwContext*<br/>
작업에 대 한 컨텍스트 식별자입니다. 참조 **주의** 에 대 한 자세한 내용은 *dwContext*합니다.

### <a name="remarks"></a>설명

기본값 *dwContext* MFC에서 전송한 합니다 `CGopherFileFind` 에서 개체를 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체를 `CGopherFileFind` 개체입니다. 생성 하는 경우는 `CGopherFileFind` 개체를 원하는 값으로 컨텍스트 식별자를 설정 하려면 기본값을 재정의할 수 있습니다. 컨텍스트 식별자에 반환 됩니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체의 상태를 제공 합니다. 문서를 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.

##  <a name="findfile"></a>  CGopherFileFind::FindFile

Gopher 파일을 찾으려면이 멤버 함수를 호출 합니다.

```
virtual BOOL FindFile(
    CGopherLocator& refLocator,
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

virtual BOOL FindFile(
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>매개 변수

*refLocator*<br/>
에 대 한 참조를 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.

*pstrString*<br/>
파일 이름을 포함 하는 문자열에 대 한 포인터입니다.

*dwFlags*<br/>
이 세션을 처리 하는 방법을 설명 하는 플래그입니다. 유효한 플래그는 다음과 같습니다.

- INTERNET_FLAG_RELOAD 로컬로 캐시 된 경우에 원격 서버에서 데이터를 가져옵니다.

- 로컬 또는 gateways에는 데이터를 캐시 하지 INTERNET_FLAG_DONT_CACHE 마십시오.

- Secure Sockets Layer 또는 pct. 통신 중에 보안 트랜잭션 INTERNET_FLAG_SECURE 요청 이 플래그는 HTTP 요청에만 적용 됩니다.

- 가능 하다 면 INTERNET_FLAG_USE_EXISTING 새로운 서버로 기존 연결을 다시 사용 `FindFile` 각 요청에 대 한 새 세션을 만드는 대신 요청 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 가져오기, Win32 함수 호출 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)합니다.

### <a name="remarks"></a>설명

호출한 후 `FindFile` 개체를 가져와 첫 번째 gopher를 호출할 수 있습니다 [FindNextFile](#findnextfile) 후속 gopher 파일을 검색 합니다.

##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile

호출 하 여 시작 파일을 검색 하려면이 멤버 함수 호출 [CGopherFileFind::FindFile](#findfile)합니다.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>반환 값

더 많은 파일; 없으면 0이 아닌 값 파일을 찾을 수는 디렉터리에 마지막 또는 오류가 발생 한 경우 0입니다. 확장 오류 정보를 가져오기, Win32 함수 호출 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)합니다. 찾은 파일 디렉터리에 마지막 파일 되었거나 일치 하는 경우에 파일을 찾을 수 있습니다는 `GetLastError` ERROR_NO_MORE_FILES를 반환 합니다.

##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime

현재 파일에 대 한 생성 시간을 가져옵니다.

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

성공 하면 0이 아닌 값 실패 한 경우 0입니다. `GetCreationTime` 경우에 0을 반환 합니다 [FindNextFile](#findnextfile) 이 호출한 적 `CGopherFileFind` 개체입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetCreationTime`합니다.

> [!NOTE]
>  일부 파일 시스템에서는 동일한 의미 체계를 사용 하 여이 함수에서 반환 된 타임 스탬프를 구현 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조 된 [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간은 영역 로컬 컴퓨터에 파일이 배치 된 시간에서입니다. Win32를 참조 하세요 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API 자세한 정보.

##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime

지정된 된 파일을 마지막으로 액세스 한 시간을 가져옵니다.

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

성공 하면 0이 아닌 값 실패 한 경우 0입니다. `GetLastAccessTime` 경우에 0을 반환 합니다 [FindNextFile](#findnextfile) 이 호출한 적 `CGopherFileFind` 개체입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastAccessTime`합니다.

> [!NOTE]
>  일부 파일 시스템에서는 동일한 의미 체계를 사용 하 여이 함수에서 반환 된 타임 스탬프를 구현 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조 된 [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간은 영역 로컬 컴퓨터에 파일이 배치 된 시간에서입니다. Win32를 참조 하세요 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API 자세한 정보.

##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime

파일을 변경한 마지막 시간을 가져옵니다.

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

성공 하면 0이 아닌 값 실패 한 경우 0입니다. `GetLastWriteTime` 경우에 0을 반환 합니다 [FindNextFile](#findnextfile) 이 호출한 적 `CGopherFileFind` 개체입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastWriteTime`합니다.

> [!NOTE]
>  일부 파일 시스템에서는 동일한 의미 체계를 사용 하 여이 함수에서 반환 된 타임 스탬프를 구현 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조 된 [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간은 영역 로컬 컴퓨터에 파일이 배치 된 시간에서입니다. Win32를 참조 하세요 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API 자세한 정보.

##  <a name="getlength"></a>  CGopherFileFind::GetLength

찾은 파일의 바이트의 길이 가져오려면이 함수를 호출 합니다.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>반환 값

찾은 파일의 길이 (바이트) 합니다.

### <a name="remarks"></a>설명

`GetLength` Win32 구조를 사용 하 여 [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) 값을 가져올 파일 크기 (바이트)에서입니다.

> [!NOTE]
>  MFC 7.0부터 `GetLength` 64 비트 정수 형식을 지원 합니다. 기존 코드를이 최신 버전의 라이브러리를 사용 하 여 빌드한 잘림 경고가 발생할 수 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (기본 클래스 구현).

##  <a name="getlocator"></a>  CGopherFileFind::GetLocator

가져오려면이 함수를 호출 합니다 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체를 [FindFile](#findfile) gopher 파일을 찾기 위해 사용 합니다.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>반환 값

`CGopherLocator` 개체입니다.

##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName

Gopher 화면의 이름을 가져오려면이 함수를 호출 합니다.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>반환 값

Gopher 화면의 이름입니다.

##  <a name="isdots"></a>  CGopherFileFind::IsDots

파일을 반복 하는 동안 현재 디렉터리 및 부모 디렉터리 표식에 대 한 테스트 합니다.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>반환 값

찾은 파일 이름을 가진 경우 0이 아닌 "."또는"..."를 실제 디렉터리를 찾은 파일 임을 나타냅니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsDots`합니다.

## <a name="see-also"></a>참고자료

[CFileFind 클래스](../../mfc/reference/cfilefind-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind 클래스](../../mfc/reference/cftpfilefind-class.md)<br/>
[CFileFind 클래스](../../mfc/reference/cfilefind-class.md)<br/>
[CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
