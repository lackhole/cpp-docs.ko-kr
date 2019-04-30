---
title: CInternetFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
ms.openlocfilehash: 65bc36856e253d086cc430a600daa9255e21ea75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405744"
---
# <a name="cinternetfile-class"></a>CInternetFile 클래스

인터넷 프로토콜을 사용 하는 원격 시스템에서 파일에 액세스할 수 있습니다.

## <a name="syntax"></a>구문

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[CInternetFile::CInternetFile](#cinternetfile)|`CInternetFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CInternetFile::Abort](#abort)|모든 경고 및 오류를 무시 하 여 파일을 닫습니다.|
|[CInternetFile::Close](#close)|닫습니다는 `CInternetFile` 하 고 해당 리소스를 해제 합니다.|
|[CInternetFile::Flush](#flush)|쓰기 버퍼의 내용을 플러시합니다 고 메모리의 데이터를 대상 컴퓨터에 기록 됩니다.|
|[CInternetFile::GetLength](#getlength)|파일의 크기를 반환합니다.|
|[CInternetFile::Read](#read)|지정 된 바이트 수를 읽습니다.|
|[CInternetFile::ReadString](#readstring)|문자 스트림을 읽습니다.|
|[CInternetFile::Seek](#seek)|열려 있는 파일에서 포인터 위치를 변경 합니다.|
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|데이터를 읽을 버퍼의 크기를 설정 합니다.|
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|데이터를 쓸 버퍼의 크기를 설정 합니다.|
|[CInternetFile::Write](#write)|지정 된 바이트 수를 기록 합니다.|
|[CInternetFile::WriteString](#writestring)|파일에는 null로 끝나는 문자열을 씁니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CInternetFile::operator HINTERNET](#operator_hinternet)|인터넷 핸들에 대 한 캐스팅 연산자입니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CInternetFile::m_hFile](#m_hfile)|파일 핸들입니다.|

## <a name="remarks"></a>설명

에 대 한 기본 클래스를 제공 합니다 [CHttpFile](../../mfc/reference/chttpfile-class.md) 하 고 [CGopherFile](../../mfc/reference/cgopherfile-class.md) 파일 클래스입니다. 되지 만들기는 `CInternetFile` 직접 개체입니다. 대신 호출 하 여 파생된 클래스 중 하나의 개체를 만듭니다 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) 하거나 [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)합니다. 만들 수도 있습니다는 `CInternetFile` 개체를 호출 하 여 [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)합니다.

`CInternetFile` 멤버 함수 `Open`를 `LockRange`, `UnlockRange`, 및 `Duplicate` 에 대 한 구현 되지 않은 `CInternetFile`합니다. 이러한 함수를 호출 하는 경우는 `CInternetFile` 개체를 받을 수는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.

하는 방법에 자세히 알아보려면 `CInternetFile` 문서를 참조 하는 다른 인터넷 MFC 클래스와 함께 작동 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

##  <a name="abort"></a>  CInternetFile::Abort

이 개체와 연결 된 파일을 닫고 파일을 읽거나 쓰기 위해 사용할 수 없게 하 게 합니다.

```
virtual void Abort();
```

### <a name="remarks"></a>설명

개체를 소멸 하기 전에 파일을 닫지 않은 경우 소멸자를 닫습니다.

예외를 처리 하는 경우 `Abort` 에서 서로 다릅니다 [닫기](#close) 중요 한 두 가지가 있습니다. 첫 번째는 `Abort` 함수는 예외를 throw 하지 오류에 오류를 무시 하기 때문에 있습니다. 두 번째로 `Abort` 하지 않습니다 **ASSERT** 파일이 아직 열려 있지 않거나 이전에 종료 되었습니다.

##  <a name="cinternetfile"></a>  CInternetFile::CInternetFile

이 멤버 함수를 호출 하는 경우는 `CInternetFile` 개체가 만들어집니다.

```
CInternetFile(
    HINTERNET hFile,
    LPCTSTR pstrFileName,
    CInternetConnection* pConnection,
    BOOL bReadMode);

CInternetFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrFileName,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext,
    BOOL bReadMode);
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
인터넷 파일 핸들입니다.

*pstrFileName*<br/>
파일 이름을 포함 하는 문자열에 대 한 포인터입니다.

*pConnection*<br/>
에 대 한 포인터를 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) 개체입니다.

*bReadMode*<br/>
파일이 읽기 전용인 지 여부를 나타냅니다.

*hSession*<br/>
인터넷 세션에 대 한 핸들입니다.

*pstrServer*<br/>
서버의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*dwContext*<br/>
에 대 한 컨텍스트 식별자를 `CInternetFile` 개체입니다. 참조 [WinInet 기본 사항](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.

### <a name="remarks"></a>설명

되지 만들기는 `CInternetFile` 직접 개체입니다. 대신 호출 하 여 파생된 클래스 중 하나의 개체를 만듭니다 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) 하거나 [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)합니다. 만들 수도 있습니다는 `CInternetFile` 개체를 호출 하 여 [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)합니다.

##  <a name="close"></a>  CInternetFile::Close

닫습니다는 `CInternetFile` 하 고 해당 리소스를 해제 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

파일 쓰기에 대 한 열린 경우에 대 한 암시적 호출 [플러시](#flush) 버퍼링 된 모든 데이터를 호스트에 기록 됩니다. 호출 해야 `Close` 했으면 파일을 사용 하 여 완료 합니다.

##  <a name="flush"></a>  CInternetFile::Flush

쓰기 버퍼의 내용을 플러시하려면이 멤버 함수를 호출 합니다.

```
virtual void Flush();
```

### <a name="remarks"></a>설명

사용 하 여 `Flush` 대상 컴퓨터에 메모리의 모든 데이터는 실제로 기록 되도록 하는 호스트 컴퓨터를 사용 하 여 트랜잭션 완료를 보장 합니다. `Flush` 에 유효 `CInternetFile` 쓰기용으로 열 개체입니다.

##  <a name="getlength"></a>  CInternetFile::GetLength

파일의 크기를 반환합니다.

```
virtual ULONGLONG GetLength() const;
```

##  <a name="m_hfile"></a>  CInternetFile::m_hFile

이 개체와 연결 된 파일 핸들입니다.

```
HINTERNET m_hFile;
```

##  <a name="operator_hinternet"></a>  CInternetFile::operator HINTERNET

이 연산자를 사용 하 여 현재 인터넷 세션에 대 한 Windows 핸들을 가져올 수 있습니다.

```
operator HINTERNET() const;
```

##  <a name="read"></a>  CInternetFile::Read

부터 지정 된 메모리로 읽어이 멤버 함수 호출 *lpvBuf*는 바이트 수를 지정 *nCount*합니다.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
파일 데이터를 읽을 메모리 주소에 대한 포인터입니다.

*nCount*<br/>
쓸 바이트 수 입니다.

### <a name="return-value"></a>반환 값

버퍼로 전송된 바이트 수입니다. 반환 값 보다 작거나 *nCount* 파일의 끝에 도달한 경우입니다.

### <a name="remarks"></a>설명

실제로 읽은 바이트 수를 반환 합니다.-수 있는 숫자 보다 작거나 *nCount* 파일을 종료 하는 경우. 파일을 읽는 동안 오류가 발생 하는 경우 함수가 throw 된 [CInternetException](../../mfc/reference/cinternetexception-class.md) 오류를 설명 하는 개체입니다. 파일의 끝을 지나서 읽는 것은 오류로 간주되지 않으며 예외가 throw되지 않습니다.

모든 데이터를 검색 하도록 응용 프로그램 계속 호출 해야 합니다는 `CInternetFile::Read` 메서드에서 0을 반환할 때까지 메서드.

##  <a name="readstring"></a>  CInternetFile::ReadString

줄 바꿈 문자를 발견할 때까지 문자 스트림을 읽는 데이 멤버 함수를 호출 합니다.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
읽는 중인 줄을 수신 하는 문자열에 대 한 포인터입니다.

*nMax*<br/>
읽을 문자의 최대 수입니다.

*rString*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 읽기 줄을 받는 개체입니다.

### <a name="return-value"></a>반환 값

검색 하는 일반 데이터를 포함 하는 버퍼에 대 한 포인터를 [CInternetFile](../../mfc/reference/cinternetfile-class.md) 개체입니다. 이 메서드에 전달 된 버퍼의 데이터 형식에 관계 없이 모든 조작 데이터 (예: 유니코드로 변환) 수행 하지 않습니다, 반환된 된 데이터 구조에 매핑해야 하므로 예상 처럼 합니다 **void** <strong>\*</strong> 형식을 반환 합니다.

모든 데이터를 읽지 않고 파일의 끝에 도달 했습니다 하는 경우 NULL 아니면, 모든 데이터를 읽지 않고 부울, FALSE 이면 파일의 끝에 도달 했습니다.

### <a name="remarks"></a>설명

참조 되는 메모리에 선을 결과 함수는 *pstr* 매개 변수입니다. 문자 읽기를 중지 하 여 지정 된 문자의 최대 수에 도달 하면 *최대*합니다. 버퍼는 항상 종결 null 문자를 받습니다.

호출 하는 경우 `ReadString` 첫 번째 호출 하지 않고 [SetReadBufferSize](#setreadbuffersize), 4, 096 바이트의 버퍼를 받습니다.

##  <a name="seek"></a>  CInternetFile::Seek

이전에 연된 파일에 대 한 포인터의 위치를 변경 하려면이 멤버 함수를 호출 합니다.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>매개 변수

*lOffset*<br/>
파일에서 읽기/쓰기 포인터를 이동 하는 바이트에서 오프셋입니다.

*nFrom*<br/>
오프셋에 대 한 상대 참조 합니다. 다음 값 중 하나 여야 합니다.

- `CFile::begin` 파일 포인터를 이동 *lOff* 파일의 시작 부분에서 바이트를 전달 합니다.

- `CFile::current` 파일 포인터를 이동 *lOff* 파일의 현재 위치에서 바이트입니다.

- `CFile::end` 파일 포인터를 이동 *lOff* 파일 끝 까지의 바이트입니다. *lOff* 될 기존 검색할 음수를 제출 해야 합니다; 양수 값은 파일의 끝을 지난 검색 됩니다.

### <a name="return-value"></a>반환 값

새 바이트 요청된 된 위치 유효 하는 경우 파일 시작 부분 으로부터의 오프셋 값은 정의 고, 그렇지와 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체가 throw 됩니다.

### <a name="remarks"></a>설명

`Seek` 함수 액세스를 허용 임의 파일의 내용에 포인터를 이동 하 여 지정된 된 크기 또는 절대입니다. 검색 하는 동안 읽은 데이터가 없으면 실제로 합니다.

이때이 멤버 함수에 대 한 호출은 연관 된 데이터에 대 한 지원만 `CHttpFile` 개체입니다. FTP 또는 gopher 요청에 대 한 지원 되지 않습니다. 호출 하는 경우 `Seek` 지원 되지 않는 이러한 서비스 중 하나에 대 한 전달 다시 있습니다 ERROR_INTERNET_INVALID_OPERATION Win32 오류 코드입니다.

파일을 열면 파일 포인터가 오프셋 0, 파일의 시작 부분 에서입니다.

> [!NOTE]
>  사용 하 여 `Seek` 암시적 호출에 발생할 수 있습니다 [플러시](#flush)합니다.

### <a name="example"></a>예제

  기본 클래스 구현에 대 한 예제를 참조 하세요 ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).

##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize

사용 하는 임시 읽기 버퍼의 크기를 설정 하려면이 멤버 함수 호출을 `CInternetFile`-파생 개체입니다.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>매개 변수

*nReadSize*<br/>
원하는 버퍼 크기(바이트)입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하려면 호출 될 수 있습니다.

### <a name="remarks"></a>설명

기본 WinInet Api 버퍼링을 수행 하지 않습니다 하므로 응용 프로그램이 읽을 데이터 양에 관계 없이 효율적으로 데이터를 읽을 수 있도록 하는 버퍼 크기를 선택 합니다. 호출할 때마다 하는 경우 [읽기](#read) 일반적으로 큰 aount 포함 됩니다 (예: 4 개 이상의 킬로바이트) 데이터 필요 하면 버퍼입니다. 그러나 호출 하는 경우 `Read` 적은 양의 데이터를 가져오려면 사용 하는 경우 또는 [ReadString](#readstring) 읽기 버퍼를 응용 프로그램 성능이 향상 됩니다. 다음 번에 개별 줄을 읽을 수 있습니다.

기본적으로 `CInternetFile` 개체 읽기에 대 한 버퍼링을 제공 하지 않습니다. 이 멤버 함수를 호출 하는 경우에 파일 읽기 액세스용 열렸음을 확인 해야 합니다.

언제 든 지 버퍼 크기를 늘릴 수 있지만 버퍼 축소 영향을 주지 않습니다. 호출 하는 경우 [ReadString](#readstring) 첫 번째 호출 하지 않고 `SetReadBufferSize`, 4, 096 바이트의 버퍼를 받습니다.

##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize

사용 하는 임시 쓰기 버퍼의 크기를 설정 하려면이 멤버 함수 호출을 `CInternetFile`-파생 개체입니다.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>매개 변수

*nWriteSize*<br/>
버퍼의 크기(바이트)입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하려면 호출 될 수 있습니다.

### <a name="remarks"></a>설명

WinInet Api 버퍼링을 수행 하지 않는 기본 쓸 데이터 양에 관계 없이 효율적으로 데이터를 작성 하도록 응용 프로그램을 허용 하는 버퍼 크기를 따라서 선택 합니다. 호출할 때마다 경우 [작성](#write) 일반적으로 많이 포함 됩니다 (예를 들어, 한 번에 4 개 이상의 킬로바이트) 데이터 필요 하면 버퍼입니다. 그러나 호출 하는 경우 [쓰기](#write) 쓰기 버퍼를 적은 양의 데이터를 작성 하려면 응용 프로그램의 성능을 향상 시킵니다.

기본적으로 `CInternetFile` 개체 작성에 대 한 버퍼링을 제공 하지 않습니다. 이 멤버 함수를 호출 하는 경우 파일 쓰기 액세스용 열렸음을 확인 해야 합니다. 언제 든 지 쓰기 버퍼의 크기를 변경할 수 있지만, 이렇게 할에 대 한 암시적 호출 [플러시](#flush)합니다.

##  <a name="write"></a>  CInternetFile::Write

지정 된 메모리로 쓸이 멤버 함수 호출 *lpvBuf*는 바이트 수를 지정 *nCount*합니다.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
쓸 첫 번째 바이트에 대 한 포인터입니다.

*nCount*<br/>
쓸 바이트 수를 지정 합니다.

### <a name="remarks"></a>설명

이 함수가 throw 하는 데이터를 쓰는 동안 오류가 발생 하는 경우는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 오류를 설명 하는 개체입니다.

##  <a name="writestring"></a>  CInternetFile::WriteString

이 함수는 관련된 파일에는 null로 끝나는 문자열을 씁니다.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
쓸 콘텐츠를 포함 하는 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수가 throw 하는 데이터를 쓰는 동안 오류가 발생 하는 경우는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 오류를 설명 하는 개체입니다.

## <a name="see-also"></a>참고자료

[CStdioFile 클래스](../../mfc/reference/cstdiofile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)
