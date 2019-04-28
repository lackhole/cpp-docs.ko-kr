---
title: CStdioFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: fd42934107591905a1bbc273ee9eec4b37e58ea7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323806"
---
# <a name="cstdiofile-class"></a>CStdioFile 클래스

런타임 함수에서 연 것과 같은 C 런타임 스트림 파일을 나타내는 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)합니다.

## <a name="syntax"></a>구문

```
class CStdioFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|생성 한 `CStdioFile` 경로 또는 파일 포인터의 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CStdioFile::Open](#open)|오버로드됨. 기본적으로는 사용 하도록 설계 된 오픈 `CStdioFile` 생성자 (재정의 [CFile::Open](../../mfc/reference/cfile-class.md#open)).|
|[CStdioFile::ReadString](#readstring)|단일 텍스트 줄을 읽습니다.|
|[CStdioFile::Seek](#seek)|현재 파일 포인터를 배치합니다.|
|[CStdioFile::WriteString](#writestring)|단일 텍스트 줄을 씁니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|열려 있는 파일에 대 한 포인터를 포함합니다.|

## <a name="remarks"></a>설명

Stream 파일은 버퍼링 및 텍스트 모드 (기본값) 또는 이진 모드로 열 수 있습니다.

텍스트 모드는 캐리지 리턴-줄 바꿈 쌍에 대 한 특수 처리를 제공합니다. 줄 바꿈 문자를 작성 하는 경우 문자 (0x0a)를 텍스트 모드 `CStdioFile` 개체, 바이트 쌍 (0x0D, 0x0A) 파일로 전송 됩니다. 읽을 때, 바이트 쌍 (0x0D, 0x0A) 0x0A 싱글바이트로 변환 됩니다.

합니다 [CFile](../../mfc/reference/cfile-class.md) 함수 [중복](../../mfc/reference/cfile-class.md#duplicate)를 [LockRange](../../mfc/reference/cfile-class.md#lockrange), 및 [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) 지원 되지 않습니다 `CStdioFile`합니다.

이러한 함수를 호출 하는 경우는 `CStdioFile`를 받을 수는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

사용 하 여 대 한 자세한 내용은 `CStdioFile`, 문서를 참조 하세요 [MFC의 파일](../../mfc/files-in-mfc.md) 하 고 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="cstdiofile"></a>  CStdioFile::CStdioFile

`CStdioFile` 개체를 생성하고 초기화합니다.

```
CStdioFile();
CStdioFile(CAtlTransactionManager* pTM);
  CStdioFile(FILE* pOpenStream);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>매개 변수

*pOpenStream*<br/>
C 런타임 함수를 호출 하 여 반환 된 파일 포인터를 지정 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)합니다.

*lpszFileName*<br/>
문자열을 원하는 파일의 경로를 지정 합니다. 상대 또는 절대 경로일 수 있습니다.

*nOpenFlags*<br/>
파일 만들기, 파일 공유 및 파일 액세스 모드에 대 한 옵션을 지정 합니다. 비트 OR를 사용 하 여 여러 옵션을 지정할 수 있습니다 ( **|** ) 연산자.

한 파일 액세스 모드 옵션은 필요 합니다. 다른 모드는 선택적입니다. 참조 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) 모드 옵션 및 기타 플래그의 목록은 합니다. Mfc 3.0 이상 버전에서는 공유 플래그 허용 됩니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

기본 생성자는 파일을 연결 하지 않습니다는 `CStdioFile` 개체입니다. 이 생성자를 사용 하는 경우 사용 해야 합니다 `CStdioFile::Open` 파일을 열에 연결 하는 메서드를 `CStdioFile` 개체입니다.

단일 매개 변수는 열려 있는 파일 스트림을 첨부 된 `CStdioFile` 개체입니다. 미리 정의 된 입/출력 파일 포인터를 포함 하는 포인터 값 허용 *stdin*를 *stdout*, 또는 *stderr*합니다.

두 매개 변수 생성자를 만듭니다를 `CStdioFile` 개체를 만들고 지정된 된 경로 사용 하 여 해당 파일을 엽니다.

에 대 한 NULL을 전달 하는 경우 *pOpenStream* 또는 *lpszFileName*, 생성자가 throw를 `CInvalidArgException*`입니다.

생성자를 throw 하는 파일을 열거나 만들 수 없습니다, 하는 경우는 `CFileException*`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

##  <a name="m_pstream"></a>  CStdioFile::m_pStream

합니다 `m_pStream` C 런타임 함수에서 반환 된 데이터 멤버는 열려 있는 파일에 대 한 포인터 `fopen`합니다.

```
FILE* m_pStream;
```

### <a name="remarks"></a>설명

파일을 열어본 적 또는 닫힌 경우 NULL입니다.

##  <a name="open"></a>  CStdioFile::Open

오버로드됨. 기본적으로는 사용 하도록 설계 된 오픈 `CStdioFile` 생성자입니다.

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
문자열은 원하는 파일을 경로입니다. 상대 또는 절대 경로일 수 있습니다.

*nOpenFlags*<br/>
공유 및 액세스 모드입니다. 파일을 열 때 수행할 동작을 지정 합니다. 비트 OR를 사용 하 여 옵션을 결합할 수 있습니다 (&#124;) 연산자. 에 대 한 액세스 권한과 하나 공유 옵션은 필요한; modeCreate 및 modeNoInherit 모드는 선택적입니다.

*pError*<br/>
실패 한 작업의 상태를 수신 하는 기존 파일 예외 개체에 대 한 포인터입니다.

*pTM*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="readstring"></a>  CStdioFile::ReadString

텍스트 데이터의 제한까지 버퍼로 읽습니다 *최대*연관 된 파일에서-1 문자는 `CStdioFile` 개체입니다.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
Null로 끝나는 문자열을 받는 사용자가 제공한 버퍼에 대 한 포인터를 지정 합니다.

*nMax*<br/>
제외 하 고 null 종결 문자를 읽을 문자의 최대 수를 지정 합니다.

*rString*<br/>
에 대 한 참조를 `CString` 함수에서 반환 된 문자열을 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

텍스트 데이터를 포함 하는 버퍼에 대 한 포인터입니다. 모든 데이터를 읽지 않고 파일의 끝에 도달 했습니다 하는 경우 NULL 아니면 모든 데이터를 읽지 않고 부울, FALSE 이면 파일의 끝에 도달 했습니다.

### <a name="remarks"></a>설명

첫 번째 줄 바꿈 문자로 읽기 중지 됩니다. 보다 적은 경우 if *최대*-1 문자를 읽은, 줄 바꿈 문자 버퍼에 저장 됩니다. Null 문자 ('\0')는 두 경우 모두 추가 됩니다.

[CFile::Read](../../mfc/reference/cfile-class.md#read) 캐리지 리턴-줄 바꿈 쌍에 텍스트 모드 입력 하지만 종료 하지 않는 한 사용할 수도 있습니다.

> [!NOTE]
>  합니다 `CString` 이 함수의 버전을 제거 합니다 `'\n'` 있으면 LPTSTR 버전은 그렇지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

##  <a name="seek"></a>  CStdioFile::Seek

이전에 연된 파일에 대 한 포인터를 다시 설정합니다.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>매개 변수

*lOff*<br/>
포인터를 이동 하는 바이트 수입니다.

*nFrom*<br/>
포인터 이동 모드입니다. 다음 값 중 하나 여야 합니다.

- `CFile::begin`: 파일 포인터를 이동 *lOff* 파일의 시작 부분에서 바이트를 전달 합니다.

- `CFile::current`: 파일 포인터를 이동 *lOff* 파일의 현재 위치에서 바이트입니다.

- `CFile::end`: 파일 포인터를 이동 *lOff* 파일 끝 까지의 바이트입니다. 사실은 *lOff* 될 기존 검색할 음수를 제출 해야 합니다; 양수 값은 파일의 끝을 지난 검색 됩니다.

### <a name="return-value"></a>반환 값

요청 된 위치가 유효 `Seek` 파일의 시작 부분에서 새 바이트 오프셋을 반환 합니다. 그렇지 않은 경우 반환 값은 정의 되지 않습니다 및 `CFileException` 개체가 throw 됩니다.

### <a name="remarks"></a>설명

`Seek` 함수 액세스를 허용 임의 파일의 내용에 포인터를 이동 하 여 지정된 된 크기 또는 절대입니다. 검색 하는 동안 읽은 데이터가 없으면 실제로 합니다. 요청 된 위치가 파일의 크기 보다 큰 경우 해당 위치로 확장 되도록 파일 길이 및 예외가 throw 됩니다.

파일을 열면 파일 포인터는 오프셋 0, 파일의 시작 부분에 배치 됩니다.

이 구현의 `Seek` 런타임 라이브러리 (CRT) 함수를 기반으로 하는 `fseek`합니다. 사용에는 몇 가지 제한이 `Seek` 텍스트 모드에서 열린 스트림에서 합니다. 자세한 내용은 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)합니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법을 보여 줍니다 `Seek` 의 시작 부분에서 1000 바이트 포인터를 이동 하 여 `cfile` 파일입니다. 사실은 `Seek` 이후에 호출 해야 하므로 데이터를 읽지 않습니다 [CStdioFile::ReadString](#readstring) 데이터를 읽을 수 있습니다.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

##  <a name="writestring"></a>  CStdioFile::WriteString

버퍼에서 데이터를 연결 된 파일을 쓸는 `CStdioFile` 개체입니다.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
Null로 끝나는 문자열을 포함 하는 버퍼에 대 한 포인터를 지정 합니다.

### <a name="remarks"></a>설명

Null 종결 문자 ( `\0`) 파일에 기록 되지 않습니다. 이 메서드는 줄 바꿈 문자를 씁니다 *lpsz* 캐리지 리턴/줄 바꿈 쌍으로 파일에 있습니다.

파일을 사용 하 여 null로 종결 되지 않은 데이터를 작성 하려는 경우 `CStdioFile::Write` 나 [CFile::Write](../../mfc/reference/cfile-class.md#write)합니다.

이 메서드에서 throw 한 `CInvalidArgException*` NULL을 지정 하는 경우는 *lpsz* 매개 변수.

이 메서드에서 throw 한 `CFileException*` 파일 시스템 오류에 대 한 응답에서입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>참고자료

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[CNotSupportedException 클래스](../../mfc/reference/cnotsupportedexception-class.md)
