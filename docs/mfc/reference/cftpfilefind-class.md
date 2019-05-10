---
title: CFtpFileFind 클래스
ms.date: 11/04/2016
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
ms.openlocfilehash: 5da739cac1ab852ce64526b24ee2b4f66d40d570
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182136"
---
# <a name="cftpfilefind-class"></a>CFtpFileFind 클래스

FTP 서버의 인터넷 파일 검색에 유용합니다.

## <a name="syntax"></a>구문

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|`CFtpFileFind` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFtpFileFind::FindFile](#findfile)|FTP 서버의 파일을 찾습니다.|
|[CFtpFileFind::FindNextFile](#findnextfile)|파일 검색에 대 한 이전 호출에서 계속 [FindFile](#findfile)합니다.|
|[CFtpFileFind::GetFileURL](#getfileurl)|찾은 파일의 경로 포함 하 여 URL을 가져옵니다.|

## <a name="remarks"></a>설명

`CFtpFileFind` 검색을 시작 파일을 찾아 URL 또는 파일에 대 한 설명이 포함 된 기타 정보를 반환 하는 멤버 함수를 포함 합니다.

인터넷 및 검색 하는 로컬 파일 포함을 위해 설계 된 다른 MFC 클래스 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 하 고 [CFileFind](../../mfc/reference/cfilefind-class.md)합니다. 와 함께 `CFtpFileFind`, 이러한 클래스는 프로토콜 또는 파일 유형 (로컬 컴퓨터 또는 원격 서버) 서버에 관계 없이 특정 파일을 찾으려면 클라이언트에 대 한 원활 하 게 메커니즘을 제공 합니다. HTTP 검색에 필요한 파일을 직접 조작을 지원 하지 않으므로 HTTP 서버에서 검색 하는 데 없는 MFC 클래스는 참고 합니다.

사용 하는 방법에 대 한 자세한 내용은 `CFtpFileFind` 문서를 참조 하는 다른 WinInet 클래스 및 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.

## <a name="example"></a>예제

다음 코드에는 FTP 서버의 현재 디렉터리의 모든 파일을 열거 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

##  <a name="cftpfilefind"></a>  CFtpFileFind::CFtpFileFind

이 멤버 함수를 생성 하 라고는 `CFtpFileFind` 개체입니다.

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pConnection*<br/>
`CFtpConnection` 개체에 대한 포인터입니다. 호출 하 여 FTP 연결을 가져올 수 있습니다 [cinternetsession:: Getftpconnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)합니다.

*dwContext*<br/>
에 대 한 컨텍스트 식별자를 `CFtpFileFind` 개체입니다. 참조 **주의** 이 매개 변수에 대 한 자세한 내용은 합니다.

### <a name="remarks"></a>설명

기본값 *dwContext* MFC에서 전송한 합니다 `CFtpFileFind` 에서 개체를 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체를 `CFtpFileFind` 개체입니다. 원하는 값으로 컨텍스트 식별자를 설정 하려면 기본값을 재정의할 수 있습니다. 컨텍스트 식별자에 반환 됩니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체의 상태를 제공 합니다. 문서를 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.

### <a name="example"></a>예제

  이 항목의 앞부분에 있는 클래스 개요의 예제를 참조 하세요.

##  <a name="findfile"></a>  CFtpFileFind::FindFile

FTP 파일을 확인 하려면이 멤버 함수를 호출 합니다.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>매개 변수

*pstrName*<br/>
검색할 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다. NULL 인 경우 호출 됩니다 (*) 와일드 카드 검색을 수행 합니다.

*dwFlags*<br/>
이 세션을 처리 하는 방법을 설명 하는 플래그입니다. 이러한 플래그는 비트 OR 연산자를 함께 사용할 수 있습니다 (&#124;)와 같습니다.

- INTERNET_FLAG_RELOAD 로컬로 캐시 된 경우에 연결에서 데이터를 가져옵니다. 이것이 기본 플래그입니다.

- 로컬 또는 gateways에는 데이터를 캐시 하지 INTERNET_FLAG_DONT_CACHE 마십시오.

- INTERNET_FLAG_RAW_DATA 원시 데이터를 반환 하도록 기본값을 재정의 ( [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) FTP에 대 한 구조).

- Secure Sockets Layer 또는 pct.를 사용 하 여 통신 중에 트랜잭션을 INTERNET_FLAG_SECURE 보호 이 플래그는 HTTP 요청에만 적용 됩니다.

- 가능 하다 면 INTERNET_FLAG_EXISTING_CONNECT 새로운 서버로 기존 연결을 다시 사용 `FindFile` 각 요청에 대 한 새 세션을 만드는 대신 요청 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다. 확장 오류 정보를 가져오기, Win32 함수 호출 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.

### <a name="remarks"></a>설명

호출한 후 `FindFile` 첫 번째 FTP 파일을 검색 하려면 호출할 수 있습니다 [FindNextFile](#findnextfile) 후속 FTP 파일을 검색 합니다.

### <a name="example"></a>예제

  이 항목의 이전 예제를 참조 하세요.

##  <a name="findnextfile"></a>  CFtpFileFind::FindNextFile

에 대 한 호출으로 시작 하는 파일 검색을 계속 하려면이 멤버 함수를 호출 합니다 [FindFile](#findfile) 멤버 함수입니다.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>반환 값

더 많은 파일; 없으면 0이 아닌 값 파일을 찾을 수는 디렉터리에 마지막 또는 오류가 발생 한 경우 0입니다. 확장 오류 정보를 가져오기, Win32 함수 호출 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)합니다. 찾은 파일 디렉터리에 마지막 파일 되었거나 일치 하는 경우에 파일을 찾을 수 있습니다는 `GetLastError` ERROR_NO_MORE_FILES를 반환 합니다.

### <a name="remarks"></a>설명

이 함수 특성 함수를 호출 하기 전에 한 번 이상 호출 해야 합니다 (참조 [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).

`FindNextFile` Win32 함수를 래핑하고 [FindNextFile](/windows/desktop/api/fileapi/nf-fileapi-findnextfilea)합니다.

### <a name="example"></a>예제

  이 항목 앞부분에 나오는 예제를 참조 하세요.

##  <a name="getfileurl"></a>  CFtpFileFind::GetFileURL

지정된 된 파일의 URL을 가져오려면이 함수를 호출 합니다.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>반환 값

Universal Resource Locator (URL)의 경로 파일입니다.

### <a name="remarks"></a>설명

`GetFileURL` 멤버 함수에 비슷합니다 [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)형태로 URL을 반환 하는 점을 제외 하 고, `ftp://moose/dir/file.txt`합니다.

## <a name="see-also"></a>참고자료

[CFileFind 클래스](../../mfc/reference/cfilefind-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind 클래스](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
